<script>
  let vhs = false
  function handleToggle (){
    vhs = !vhs
  }

  $:console.log(vhs)
</script>

<div class="container {vhs?"vhs":""}">
  <nav>
    <a href="#">CONTACT</a>
    <a href="#">ABOUT</a>
    <a href="/projects" class="buy">Projects</a>
  </nav>
  <div class="main-container">
    <div class="text-sphere-container">
      <div class="text-container">
        <h1>Hashim Kader</h1>
        <h2>SOFTWARE, AI AND MACHINE LEARNING ENGINEER</h2>
        <h3>BSc AI/ML Eng</h3>
        <!-- <p>Couldnt really think of anything to put here but the space kinda looks empty without it no?</p> -->
        <a href="/projects" class="buy-cta">View Projects</a>
      </div>
      <a href="">
        <div class="sphere"></div>
      </a>
    </div>
    <div class="learn-arrow">
      <!-- <button on:click={handleToggle}>click me</button> -->
    </div>
  </div>
</div>

<style>
  @import url("https://fonts.googleapis.com/css2?family=DM+Serif+Display:ital@0;1&family=Mulish:ital,wght@0,200..1000;1,200..1000&family=Playfair+Display:ital,wght@0,400..900;1,400..900&family=Work+Sans:ital,wght@0,100..900;1,100..900&display=swap");

:root {
  --dark-color: 	#15251fe4;
  --mid-dark: #555a57;
  --light-color: #ece0c8;
  --mid-light: #fffee5c9;
  --shadow: #0005;
  --linear-rainbow: linear-gradient(
    to right,#ede6bf,#ecc947,#cb5a31,#6f5d79,#4e779a
  );
  --circle-rainbow: radial-gradient(
    circle at left top,#ede6bf,#ecc947,#cb5a31,#6f5d79,#4e779a
  );
  --noise-texture: url(https://i.gyazo.com/a26366e538851a5c569ff648e99b7fd4.png);
  --gif-texture: url(https://64.media.tumblr.com/da60c13b478dda09ab90c27e880983b8/tumblr_nd4pwdPKdc1tun3l0o1_1280.gifv);
}

h1 {
  margin: 0;
  font-family: "Mulish", sans-serif;
  font-weight: 1000;
  font-size: 64px;
  color: var(--light-color);
  text-align: left;
}

h2 {
  margin: 0;
  font-family: "Playfair Display", serif;
  font-size: 16px;
  color: var(--mid-light);
  text-align: left;
}

h3 {
  margin: 0;
  font-family: "DM Serif Display", serif;
  font-size: 24px;
  color: var(--mid-light);
  text-align: left;
  margin-bottom: 8px;
}

p {
  font-family: "Mulish", sans-serif;
  font-weight: 700;
  width: 390px;
  color: var(--mid-light);
  text-align: left;
}

nav {
  display: flex;
  align-items: center;
  justify-content: end;
  box-sizing: border-box;
  margin: 30px 128px;
  gap: 48px;
  font-size: 16px;
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

.container {
  margin: 0;
  padding: 0;
  display: flex;
  flex-direction: column;
  height: 100vh;
  width: 100%;
  
  box-sizing: border-box;
/*   scale:2; */
  animation: spawn 2s ease-in-out forwards; 
}

.container:before {
  content: "";
  display: flex;
  position: absolute;
  background-image: var(--noise-texture);
  /* height: 100%; */
  width: 100%;
  mix-blend-mode: overlay;
  pointer-events: none;
  z-index: 3;
}

.vhs:after {
  content: "";
  display: flex;
  position: absolute;
  background-image: var(--gif-texture);
  height: 100%;
  width: 100%;
  background-repeat: no-repeat;
  background-size: cover;
  mix-blend-mode: screen;
  pointer-events: none;
  opacity: 64%; 
  z-index: 3;
}

.main-container {
  padding: 0;
  margin: auto;
  display: grid;
  height: 100%;
  gap: 64px;
  place-items: center;
  box-sizing: border-box;
}

.text-container {
  display: flex;
  flex-direction: column;
  align-items: flex-start;  
}

.text-sphere-container {
  display: flex;
  width: 125%;
  gap: 128px;
  align-items: center;  
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

.buy {
  display: grid;
  place-items: center;
  font-weight: 900;
  border: 1px solid var(--mid-light);
  height: 40px;
  width: 128px;
  transition: all 0.2s;
}

.buy:hover {
  scale: 1.1;
  background: var(--light-color);
  color: var(--dark-color);
  border: 1px solid var(--light-color);
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

.learn-arrow {
  margin: -40px 0;
  text-align: center;
  transition: all 0.2s;
}

.learn:hover {
  scale: 1.2;
  font-weight: 900;
}

.learn {
  display: grid;
  color: var(--light-color);
  font-family: "Mulish", sans-serif;
  font-weight: 400;
  cursor: pointer;
  font-size: 12px;
}

.arrow {
  margin: -6px;
  padding: 0;
  font-size: 32px;
  color: var(--light-color);
}

/* @keyframes spawn{
  0%{
    box-shadow: 0 0 0 var(--shadow);
    opacity:0%;
  }
  100%{
    box-shadow: 0 0 32px var(--shadow);
    opacity:100%;
  }
} */
</style>