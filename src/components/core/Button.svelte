<script lang="ts">
  export let title
  export let href
  export let size: "sm" | "md" | "lg" = "sm"
</script>

<a class="button-container-3 {size}" href={href}>
  <span class="mas">{title}</span>
  <button type="button" name="Hover">{title}</button>
</a>

<style>
  .mas {
  position: absolute;
  color: #ece0c8;
  text-align: center;
  width: 100%;
  font-family: "Lato", sans-serif;
  font-weight: 300;
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

.sm{
  width: 100px;
}

.md{
  width: 150px;
}

.lg{
  width: 250px;
}

.button-container-3 {
  position: relative;
  height: 50px;
  /* margin-left: auto;
  margin-right: auto; */
  /* margin-top: 8vh; */
  overflow: hidden;
  border: 1px solid #ece0c8;
  font-family: "Lato", sans-serif;
  font-weight: 300;
  transition: 0.5s;
  letter-spacing: 1px;
  border-radius: 8px;
}
.button-container-3:active {
  transform: scale(0.9);
}
.button-container-3 button {
  width: 100%;
  height: 100%;
  font-family: "Lato", sans-serif;
  font-weight: 300;
  font-size: 11px;
  letter-spacing: 1px;
  font-weight: bold;
  background: #ece0c8;
  -webkit-mask: url("https://raw.githubusercontent.com/pizza3/asset/master/natureSmaller.png");
  mask: url("https://raw.githubusercontent.com/pizza3/asset/master/natureSmaller.png");
  -webkit-mask-size: 7100% 100%;
  mask-size: 7100% 100%;
  border: none;
  color: #15251fe4;
  cursor: pointer;
  -webkit-animation: ani2 0.7s steps(70) forwards;
  animation: ani2 0.7s steps(70) forwards;
}
.button-container-3 button:hover {
  -webkit-animation: ani 0.7s steps(70) forwards;
  animation: ani 0.7s steps(70) forwards;
}
</style>