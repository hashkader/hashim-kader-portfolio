<script>
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
</style>
