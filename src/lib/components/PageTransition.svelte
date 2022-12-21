<script lang="ts"> 
  	import { gsap } from 'gsap/dist/gsap';
	import { onMount } from 'svelte';

  onMount(()=> {
    const svg = document.getElementById("svg");
const tl = gsap.timeline();
const curve = "M0 502S175 272 500 272s500 230 500 230V0H0Z";
const flat = "M0 2S175 1 500 1s500 1 500 1V0H0Z";

tl.from(".loader-wrap-heading h1", {
  delay: .5,
  y: 300,
  skewY: 10,
}).to(".loader-wrap-heading h1", {
  opacity: 0,
  delay: 1.5,
  y: -200,
  skewY: 10,
  ease: "power2.easeOut"
});
tl.to(svg, {
  duration: 0.8,
  attr: { d: curve },
  ease: "power2.easeIn",
}).to(svg, {
  duration: 0.8,
  attr: { d: flat },
  ease: "power2.easeOut",
});
tl.to(".loader-wrap", {
  y: -1200,
});
tl.to(".loader-wrap", {
  zIndex: -1,
  display: "none",
});
tl.from(
  ".container h1",
  {
    y: 100,
    opacity: 0,
  },
  "-=1.5"
);
  })
</script>

<div class="loader-wrap">
  <svg viewBox="0 0 1000 1000" preserveAspectRatio="none" fill="#6A2E35">
    <path id="svg" d="M0,1005S175,995,500,995s500,5,500,5V0H0Z"></path>
  </svg>

  <div class="loader-wrap-heading">
    <span><h1>LOADING...</h1></span>
  </div>
</div>

<style>

span {
  overflow: hidden;
  display: block;
}

.loader-wrap {
  position: absolute;
  z-index: 10;
  height: 100vh;
  width: 100%;
  display: flex;
  overflow: hidden;
  align-items: center;
  justify-content: center;
  background: transparent;
}

.loader-wrap svg {
  position: absolute;
  top: 0;
  width: 100vw;
  height: 110vh;
}

.loader-wrap .loader-wrap-heading h1 {
  font-size: 5rem;
  z-index: 20;
  color: var(--color-white);
  text-transform: uppercase;
  font-weight: lighter;
}

@media (max-width: 767px) {
  .loader-wrap svg {
    width: 200vw;
    margin-left: -50vw;
  }
  .loader-wrap .loader-wrap-heading {
    font-size: 60px;
  }
}
</style>
