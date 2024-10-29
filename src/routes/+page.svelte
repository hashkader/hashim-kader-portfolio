<!-- <script>
  import PageWrapper from "../components/core/PageWrapper.svelte";
  import Header from "../components/core/Header.svelte";
</script>

<PageWrapper>
  <Header/>
</PageWrapper>

<style>
  @import url("https://fonts.googleapis.com/css2?family=DM+Serif+Display:ital@0;1&family=Mulish:ital,wght@0,200..1000;1,200..1000&family=Playfair+Display:ital,wght@0,400..900;1,400..900&family=Work+Sans:ital,wght@0,100..900;1,100..900&display=swap");

  :root {
    --dark-color: #15251fe4;
    --mid-dark: #555a57;
    --light-color: #ece0c8;
    --mid-light: #fffee5c9;
    --shadow: #0005;
    --linear-rainbow: linear-gradient(
      to right,
      #ede6bf,
      #ecc947,
      #cb5a31,
      #6f5d79,
      #4e779a
    );
    --circle-rainbow: radial-gradient(
      circle at left top,
      #ede6bf,
      #ecc947,
      #cb5a31,
      #6f5d79,
      #4e779a
    );
    --noise-texture: url(https://i.gyazo.com/a26366e538851a5c569ff648e99b7fd4.png);
    --gif-texture: url(https://64.media.tumblr.com/da60c13b478dda09ab90c27e880983b8/tumblr_nd4pwdPKdc1tun3l0o1_1280.gifv);
  }

  h1 {
    margin: 0;
    font-family: "Mulish", sans-serif;
    font-weight: 1000;
    font-size: 64px;
    line-height: 72px;
    color: var(--light-color);
    text-align: left;
  }

  h2 {
    margin: 0;
    font-family: "Mulish", sans-serif;
    font-weight: 700;
    font-size: 24px;
    color: var(--light-color);
    text-align: left;
    padding-bottom: 4px;
  }

  h3 {
    margin: 0;
    font-family: "Mulish", sans-serif;
    font-weight: 700;
    font-size: 16px;
    color: var(--light-color);
    text-align: left;
    padding-bottom: 16px;
  }

  a {
    box-sizing: border-box;
    margin: 0;
    padding: 0;
    font-size: 12px;
    font-family: "Mulish", sans-serif;
    color: var(--mid-light);
    font-weight: 400;
    text-decoration: none;
  }

  a:not(.buy, .buy-cta, .learn) {
    width: 64px;
  }

  a:hover:not(.buy, .buy-cta, .learn) {
    transition: all 0.2s ease-in-out;
    font-weight: 900;
    text-shadow: 0 0 8px var(--light-color);
  }

  .text-container {
    display: flex;
    flex-direction: column;
    align-items: flex-start;
  }

  .sphere {
    display: grid;
    height: 200px;
    width: 200px;
    background-image: var(--circle-rainbow);
    border: 3px solid var(--dark-color);
    border-radius: 50%;
    transition: all 0.4s;
    box-shadow: 0px 0px var(--shadow);
  }

  .sphere:hover {
    scale: 1.1;
    box-shadow: 16px 16px var(--shadow);
    transition: all 0.2s;
  }

  .buy-cta {
    display: grid;
    place-items: center;
    color: var(--dark-color);
    font-weight: 900;
    background-image: linear-gradient(
      to right,
      var(--light-color),
      var(--light-color)
    );
    height: 40px;
    width: 200px;
    font-size: 16px;
    transition: all 0.4s;
  }

  .buy-cta:hover {
    scale: 1.1;
    color: var(--light-color);
    background-image: var(--linear-rainbow);
    transition: all 0.2s;
  }
</style> -->

<script lang="ts">
  import { onMount } from 'svelte';
  import Nav from '../components/core/Nav.svelte';
  import Header from '../components/core/Header.svelte'
  import { page } from '$app/stores';
  let canvas: HTMLCanvasElement | null = null;
  let ctx: CanvasRenderingContext2D | null = null;
  let particles: Particle[] = [];
  let mouseX = 0;
  let mouseY = 0;
  let winW: number;
  let winH: number;
  let rafId: number | null = null;

  const options = {
    dotColor: '#eee',
    lineColor: '#eee',
    proximity: 100,
    particleRadius: 2,
    lineWidth: 1,
    density: 23000,
  };

  class Particle {
    position = { x: Math.random() * winW, y: Math.random() * winH };
    speed = { x: Math.random() * 1 - 0.5, y: Math.random() * 1 - 0.5 };
    radius = options.particleRadius;
    color = options.dotColor;

    updatePosition() {
      this.position.x += this.speed.x;
      this.position.y += this.speed.y;

      if (this.position.x > winW) this.position.x = 0;
      if (this.position.x < 0) this.position.x = winW;
      if (this.position.y > winH) this.position.y = 0;
      if (this.position.y < 0) this.position.y = winH;
    }

    draw() {
      if (ctx) {
        ctx.beginPath();
        ctx.arc(this.position.x, this.position.y, this.radius, 0, Math.PI * 2);
        ctx.fillStyle = this.color;
        ctx.fill();
        ctx.closePath();
      }
    }
  }

  function drawLines() {
    if (!ctx) return;

    particles.forEach((particle, i) => {
      for (let j = i + 1; j < particles.length; j++) {
        const otherParticle = particles[j];
        const dx = particle.position.x - otherParticle.position.x;
        const dy = particle.position.y - otherParticle.position.y;
        const distance = Math.sqrt(dx * dx + dy * dy);

        if (distance < options.proximity) {
          ctx.beginPath();
          ctx.moveTo(particle.position.x, particle.position.y);
          ctx.lineTo(otherParticle.position.x, otherParticle.position.y);
          ctx.strokeStyle = options.lineColor;
          ctx.lineWidth = options.lineWidth;
          ctx.stroke();
          ctx.closePath();
        }
      }
    });
  }

  function resizeCanvas() {
    winW = window.innerWidth;
    winH = window.innerHeight;
    if (canvas && ctx) {
      canvas.width = winW;
      canvas.height = winH;
    }
  }

  function draw() {
    if (ctx && canvas) {
      ctx.clearRect(0, 0, winW, winH);

      particles.forEach((particle) => {
        particle.updatePosition();
        particle.draw();
      });

      drawLines();

      rafId = requestAnimationFrame(draw);
    }
  }

  onMount(() => {
    winW = window.innerWidth;
    winH = window.innerHeight;

    canvas = document.getElementById('particle-canvas') as HTMLCanvasElement;
    ctx = canvas.getContext('2d');

    resizeCanvas();

    const numParticles = Math.floor((winW * winH) / options.density);
    particles = Array.from({ length: numParticles }, () => new Particle());

    window.addEventListener('resize', resizeCanvas);
    document.addEventListener('mousemove', (e) => {
      mouseX = e.clientX;
      mouseY = e.clientY;
    });

    rafId = requestAnimationFrame(draw);

    return () => {
      if (rafId) cancelAnimationFrame(rafId);
      window.removeEventListener('resize', resizeCanvas);
    };
  });

  
</script>

<div id="particles">
  <!-- <Nav/> -->
  <div id="intro">
    <Header/>
  </div>
  <canvas id="particle-canvas"></canvas>
</div>

<style>
  :global(body) {
    background-color: #15251fe4;
    overflow-x: hidden;
    /* overflow: hidden; */
  }

  #particles {
    position: relative;
    width: 100vw;
    height: 100vh;
    /* overflow: hidden; */
  }

  #particle-canvas {
    display: block;
    width: 100%;
    height: 100vh;
    background-size: cover;
  }

  #intro {
    position: absolute;
    top: 30%;
    width: 100%;
  }

</style>
