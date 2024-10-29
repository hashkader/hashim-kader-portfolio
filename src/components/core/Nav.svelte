<script>
  import Button from "./Button.svelte";
</script>

<nav>
  <a href="#">CONTACT</a>
  <a href="/about">ABOUT</a>
  <Button title="Projects" href="/projects"/>
  <!-- <a href="/projects" class="buy">Projects</a> -->
</nav>

<style>

@import url("https://fonts.googleapis.com/css?family=Lato:100,300,400");
@import url("https://fonts.googleapis.com/css?family=Roboto:100");

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