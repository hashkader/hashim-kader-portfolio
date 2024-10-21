<div class="text-sphere-container">
  <div class="text-container">
    <div class="text">
      <div class="name">
        <span class="letter bg" on:mouseover={applyGradient}>H</span>
        <span class="letter bg" on:mouseover={applyGradient}>A</span>
        <span class="letter bg" on:mouseover={applyGradient}>S</span>
        <span class="letter bg" on:mouseover={applyGradient}>H</span>
        <span class="letter bg" on:mouseover={applyGradient}>I</span>
        <span class="letter bg" on:mouseover={applyGradient}>M</span>
        <span class="letter bg">&nbsp</span>
        <span class="letter bg" on:mouseover={applyGradient}>K</span>
        <span class="letter bg" on:mouseover={applyGradient}>A</span>
        <span class="letter bg" on:mouseover={applyGradient}>D</span>
        <span class="letter bg" on:mouseover={applyGradient}>E</span>
        <span class="letter bg" on:mouseover={applyGradient}>R</span>
      </div>
      <div class="name" >
        <span class="letter md" on:mouseover={applyGradient}>S</span>
        <span class="letter md" on:mouseover={applyGradient}>O</span>
        <span class="letter md" on:mouseover={applyGradient}>F</span>
        <span class="letter md" on:mouseover={applyGradient}>T</span>
        <span class="letter md" on:mouseover={applyGradient}>W</span>
        <span class="letter md" on:mouseover={applyGradient}>A</span>
        <span class="letter md" on:mouseover={applyGradient}>R</span>
        <span class="letter md" on:mouseover={applyGradient}>E</span>
        <span class="letter md" on:mouseover={applyGradient}>&nbsp</span>
        <span class="letter md" on:mouseover={applyGradient}>&</span>
        <span class="letter md" on:mouseover={applyGradient}>&nbsp</span>
        <span class="letter md" on:mouseover={applyGradient}>A</span>
        <span class="letter md" on:mouseover={applyGradient}>I</span>
        <span class="letter md" on:mouseover={applyGradient}>/</span>
        <span class="letter md" on:mouseover={applyGradient}>M</span>
        <span class="letter md" on:mouseover={applyGradient}>L</span>
        <span class="letter md" on:mouseover={applyGradient}>&nbsp</span>
        <span class="letter md" on:mouseover={applyGradient}>E</span>
        <span class="letter md" on:mouseover={applyGradient}>N</span>
        <span class="letter md" on:mouseover={applyGradient}>G</span>
        <span class="letter md" on:mouseover={applyGradient}>I</span>
        <span class="letter md" on:mouseover={applyGradient}>N</span>
        <span class="letter md" on:mouseover={applyGradient}>E</span>
        <span class="letter md" on:mouseover={applyGradient}>E</span>
        <span class="letter md" on:mouseover={applyGradient}>R</span>
      </div>
      <div class="name">
        <span class="letter sm" on:mouseover={applyGradient}>B</span>
        <span class="letter sm" on:mouseover={applyGradient}>S</span>
        <span class="letter sm" on:mouseover={applyGradient}>c</span>
        <span class="letter sm" on:mouseover={applyGradient}>&nbsp</span>
        <span class="letter sm" on:mouseover={applyGradient}>A</span>
        <span class="letter sm" on:mouseover={applyGradient}>I</span>
        <span class="letter sm" on:mouseover={applyGradient}>/</span>
        <span class="letter sm" on:mouseover={applyGradient}>M</span>
        <span class="letter sm" on:mouseover={applyGradient}>L</span>
        <span class="letter sm" on:mouseover={applyGradient}>&nbsp</span>
        <span class="letter sm" on:mouseover={applyGradient}>E</span>
        <span class="letter sm" on:mouseover={applyGradient}>n</span>
        <span class="letter sm" on:mouseover={applyGradient}>g</span>
      </div>
    </div>
    <a href="/projects" class="button-cta">View Projects</a>
  </div>
  <div class="sphere"></div>
</div>

<div class="bg-gradient" style="background-clip: text;"></div>

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
    --highlight-color: null;
  }

  ::selection {
    background: var(--highlight-color);
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

  .bg{
    font-weight: 1000;
    font-size: 64px;
  }
  .md{
    font-weight: 700;
    font-size: 24px;
  }

  .sm{
    font-weight: 700;
    font-size: 16px;
  }
  .letter {
    margin: 0;
    font-family: "Mulish", sans-serif;
    color: var(--light-color);
    text-align: left;
    transition: transform 0.09s ease, background 0.4s ease;
    background-clip: text;
  }

  .letter:hover {
      transform: scale(1.1) rotate(15deg);
      animation: sway-back 0.5s ease forwards;  
      color: transparent;
  }

  .text{
    display: flex;
    flex-direction: column;
    gap: 4px;
  }

  @keyframes sway-back {
      0% {
          transform: scale(1.9) rotate(0deg) ;
      }
      50% {
          transform: scale(1.0) rotate(15deg);
      }
      70% {
          transform: scale(1.0) rotate(-5deg); 
      }
      100% {
          transform: scale(1.0) rotate(0deg); 
      }
  }


  .name{
    display: flex;
  }

  h2 {
    margin: 0;
    font-family: "Mulish", sans-serif;
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

  a:not(.button, .button-cta, .learn) {
    width: 64px;
  }

  a:hover:not(.button, .button-cta, .learn) {
    transition: all 0.2s ease-in-out;
    font-weight: 900;
    text-shadow: 0 0 8px var(--light-color);
  }

  .text-container {
    display: flex;
    flex-direction: column;
    justify-content: space-between;
  }
  
  .text-sphere-container {
    display: flex;
    gap: 128px;
    filter: drop-shadow(0.35rem 0.35rem 0.4rem rgba(0, 0, 0, 1));
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

  .button-cta {
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

  .button-cta:hover {
    scale: 1.1;
    color: var(--light-color);
    background-image: var(--linear-rainbow);
    transition: all 0.2s;
  }

  /* Gradient Animation */
  .bg-gradient {
    position: absolute;
    top: 0;
    left: 0;
    width: 100vw;
    height: 100vh;
    background: var(--linear-rainbow);
    background-size: 400%;
    z-index: -1;
    pointer-events: none;
    animation: move-gradient 5s infinite linear;
    background-clip: text;
  }

  @keyframes move-gradient {
    0% {
      background-position: 0% 50%;
    }
    100% {
      background-position: 100% 50%;
    }
  }

</style>

<script>
  import { onMount } from "svelte";

  let gradientElement;

  function applyGradient(event) {
    const gradientStyle = getComputedStyle(gradientElement);
    const backgroundPosition = gradientStyle.backgroundPosition;

    event.target.style.backgroundImage = gradientStyle.backgroundImage;
    event.target.style.backgroundPosition = backgroundPosition;
    event.target.style.backgroundSize = gradientStyle.backgroundSize;
  }

  onMount(() => {
    gradientElement = document.querySelector('.bg-gradient');
  });

  let colors = ["	#9c7248", "#926a2d", "#876127", "#7c501a", "#6f4f1d" ];

  const changeHighlightColor = () => {
    const color = colors.shift();
    document.documentElement.style.setProperty("--highlight-color", color);
    colors.push(color);
  };

  onMount(() => {
    window.addEventListener("mousedown", changeHighlightColor);
    
    return () => {
      window.removeEventListener("mousedown", changeHighlightColor);
    };
  });
</script>
