<nav>
  <a href="#">CONTACT</a>
  <a href="/about">ABOUT</a>
  <a href="/projects" class="buy">Projects</a>
  <!-- <div class="button-container-3">
    <span class="mas">MASK3</span>
    <button type="button" name="Hover">MASK3</button>
  </div> -->
</nav>

<style>

@import url("https://fonts.googleapis.com/css?family=Lato:100,300,400");
@import url("https://fonts.googleapis.com/css?family=Roboto:100");



.mas {
  position: absolute;
  color: #000;
  text-align: center;
  width: 101%;
  font-family: "Lato", sans-serif;
  font-weight: 300;
  position: absolute;
  font-size: 11px;
  margin-top: 17px;
  overflow: hidden;
  font-weight: bold;
}

@-webkit-keyframes ani {
  from {
    -webkit-mask-position: 0 0;
    mask-position: 0 0;
  }
  to {
    -webkit-mask-position: 100% 0;
    mask-position: 100% 0;
  }
}
@keyframes ani {
  from {
    -webkit-mask-position: 0 0;
    mask-position: 0 0;
  }
  to {
    -webkit-mask-position: 100% 0;
    mask-position: 100% 0;
  }
}
@-webkit-keyframes ani2 {
  from {
    -webkit-mask-position: 100% 0;
    mask-position: 100% 0;
  }
  to {
    -webkit-mask-position: 0 0;
    mask-position: 0 0;
  }
}
@keyframes ani2 {
  from {
    -webkit-mask-position: 100% 0;
    mask-position: 100% 0;
  }
  to {
    -webkit-mask-position: 0 0;
    mask-position: 0 0;
  }
}
a {
  color: #00ff95;
}

.button-container-3 {
  position: relative;
  width: 100px;
  height: 50px;
  margin-left: auto;
  margin-right: auto;
  margin-top: 8vh;
  overflow: hidden;
  border: 1px solid #000;
  font-family: "Lato", sans-serif;
  font-weight: 300;
  transition: 0.5s;
  letter-spacing: 1px;
  border-radius: 8px;
}
.button-container-3 button {
  width: 101%;
  height: 100%;
  font-family: "Lato", sans-serif;
  font-weight: 300;
  font-size: 11px;
  letter-spacing: 1px;
  font-weight: bold;
  background: #000;
  -webkit-mask: url("https://raw.githubusercontent.com/pizza3/asset/master/natureSmaller.png");
  mask: url("https://raw.githubusercontent.com/pizza3/asset/master/natureSmaller.png");
  -webkit-mask-size: 7100% 100%;
  mask-size: 7100% 100%;
  border: none;
  color: #fff;
  cursor: pointer;
  -webkit-animation: ani2 0.7s steps(70) forwards;
  animation: ani2 0.7s steps(70) forwards;
}
.button-container-3 button:hover {
  -webkit-animation: ani 0.7s steps(70) forwards;
  animation: ani 0.7s steps(70) forwards;
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
</style>