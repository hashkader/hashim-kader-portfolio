<script lang="ts">
  import { onMount } from 'svelte';

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
    density: 10000,
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

<style>
  :global(body) {
    background-color: #15251fe4;
    overflow: hidden;
  }

  #particles {
    position: relative;
    width: 100vw;
    height: 100vh;
    overflow: hidden;
  }

  #particle-canvas {
    display: block;
    width: 100%;
    height: 100%;
    background: url('http://arnaudel.perso.neuf.fr/Payekhali/Fonds/1280/AS11-40-5873.jpg') no-repeat center center;
    background-size: cover;
  }

  #intro {
    position: absolute;
    top: 50%;
    width: 100%;
    text-align: center;
    transform: translateY(-50%);
  }
</style>

<div id="particles">
  <canvas id="particle-canvas"></canvas>
  <div id="intro">
    <slot /> <!-- Content will be rendered here -->
  </div>
</div>
