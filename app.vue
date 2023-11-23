<template>
  <div class="home-container">
    <BubbleStep1 class="bubble-container" />
  </div>
</template>

<script>
import { MorphSVGPlugin } from "gsap-trial/MorphSVGPlugin";
import { gsap } from "gsap-trial";

import { ScrollTrigger } from "gsap-trial/ScrollTrigger";
gsap.registerPlugin(ScrollTrigger, MorphSVGPlugin);

export default {
  mounted: function () {
    this.scrollAnimation();
  },

  methods: {
    scrollAnimation() {
      const bubbleRound = document.querySelector("#form02");
      const bubbleStep1 = document.querySelector("#form01");

      const scaleBubbleStep1 = gsap.to(".bubble-container", {
        scale: "+=0.05",
        yoyo: true,
        ease: "power1.inOut",
        repeat: -1,
        duration: 1,
      });
      scaleBubbleStep1.resume();
      gsap
        .timeline({
          scrollTrigger: {
            trigger: ".home-container",
            start: "bottom bottom",
            end: `${window.innerHeight * 2}`,
            markers: true,
            pin: true,
            scrub: 1,
            // onScrubComplete: () => scaleBubbleStep1.resume(),
            // onUpdate: () => scaleBubbleStep1.pause(),
          },
        })
        .to(
          "#form01",
          {
            morphSVG: bubbleRound,
            ease: "sine.easeInOut",
            duration: 0.5,
          },
          "<"
        )
        .to(".bubble-container", {
          transform: "translate(100%, 190px) rotate(10deg)",
        })
        .to("#form01", {
          morphSVG: bubbleStep1,
          ease: "sine.easeInOut",
          duration: 0.5,
        })
        .to(".bubble-container", {
          transform: "translate(100%, 190px) rotate(0deg)",
          duration: 1,
        })
        .to("#form01", {
          opacity: 0,
        })
        .to(
          "#form03",
          {
            opacity: 1,
            duration: 0.5,
            ease: "easeInOut",
          },
          "<+=0.5"
        )
        .to("#form03", {
          opacity: 0,
          translateY: "5px",
          duration: 0.5,
          ease: "easeInOut",
        });
    },
  },
};
</script>

<style>
.home-container {
  position: relative;
  height: 100vh;
  background-image: url("https://images.unsplash.com/photo-1553095066-5014bc7b7f2d?q=80&w=2071&auto=format&fit=crop&ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D");
  background-position: center; /* Center the image */
  background-repeat: no-repeat; /* Do not repeat the image */
  background-size: cover; /* Resize the background image to cover the entire container */
}

.bubble-container {
  position: absolute;
  transform: translate(200%, -390px);
}

#form02 {
  visibility: hidden;
  border: "unset";
  outline: "none";
  stroke: "transparent";
}

#form03 {
  opacity: 0;
}
</style>
