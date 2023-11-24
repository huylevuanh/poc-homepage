<template>
  <div class="home-container">
    <BubbleStep1 class="bubble-step1-container" />
    <BubbleStep2 class="bubble-step2-container" />

    <div>
      <div class="title-container">
        <img class="buho-logo" src="~/assets/bg/logo_buho.png" alt="logo" />
        <h6 class="pos-title">Desliza para Descubrir</h6>
      </div>

      <span
        v-bind:style="{ fontSize: 64 + 'px', opacity: 0 }"
        class="text-intro-1"
      >
        Te ayudamos a crecer.
      </span>
      <span
        v-bind:style="{ fontSize: 64 + 'px', opacity: 0 }"
        class="text-intro-2"
      >
        Con todo tipo de<br />
        soluciones tecnológicas.
      </span>
      <span
        v-bind:style="{ fontSize: 64 + 'px', opacity: 0 }"
        class="text-intro-3"
      >
        Para todo tipo de<br />
        negocios.
      </span>
    </div>
  </div>
</template>

<script>
import { MorphSVGPlugin } from "gsap-trial/MorphSVGPlugin";
import { gsap } from "gsap-trial";
import { ScrollSmoother } from "gsap-trial/ScrollSmoother";
import { ScrollTrigger } from "gsap-trial/ScrollTrigger";
gsap.registerPlugin(ScrollTrigger, MorphSVGPlugin, ScrollSmoother);

export default {
  mounted: function () {
    this.scrollAnimation();
  },

  methods: {
    scrollAnimation() {
      ScrollSmoother.create({
        smooth: 2,
        effects: true,
      });
      gsap
        .timeline({
          scrollTrigger: {
            trigger: ".home-container",
            start: "bottom bottom",
            end: `${window.innerHeight * 5}`,
            pin: true,
            scrub: 1,
            anticipatePin: true,
          },
        })
        .to(
          ".title-container",
          {
            transform: "scale(1.1)",
          },
          "<"
        )
        .to(".title-container", {
          transform: "scale(1.2)",
        })
        .to(
          ".bubble-step1-container",
          {
            transform: "translate(20%, -40%) rotate(10deg)",
          },
          "<"
        )
        .to(".title-container", {
          opacity: 0,
          display: "none",
        })
        .to(".text-intro-1", {
          opacity: 0.5,
        })
        .to(
          ".text-intro-1",
          {
            fontSize: 96,
            opacity: 1,
          },
          "<"
        )
        .to(".bubble-step1-container", {
          transform: "translate(-50%, -40%) rotate(0deg)",
          duration: 1,
        })

        .to(".text-intro-1", {
          opacity: 0,
          display: "none",
        })
        .to(".text-intro-2", {
          opacity: 1,
          display: "block",
        })
        .to(".text-intro-2", {
          opacity: 0,
          display: "none",
        })

        .to(".bubble-step1-container", {
          opacity: 0,
        })
        .to(".bubble-step2-container", {
          opacity: 1,
        })
        .to(
          ".text-intro-3",
          {
            opacity: 0.5,
            display: "block",
            duration: 1,
          },
          "<"
        )
        .to(".text-intro-3", {
          opacity: 1,
        })
        .to(".bubble-step2-container", {
          opacity: 0,
        })
        .to(
          ".text-intro-3",
          {
            opacity: 0,
          },
          "<"
        );
    },
  },
};
</script>

<style>
.home-container {
  position: relative;
  width: 100%;
  height: 100vh;
  background-image: url("assets/bg/bg.png");
  background-position: center; /* Center the image */
  background-repeat: no-repeat; /* Do not repeat the image */
  background-size: cover;
  display: flex;
  justify-content: center;
  align-items: center;
  will-change: transform;
}

.bubble-step1-container,
.bubble-step2-container {
  position: absolute;
  top: 50%;
  left: 50%;
}

.bubble-step1-container {
  transform: translate(60%, -90%);
}

.bubble-step2-container {
  transform: translate(-35%, -40%);
}

.pre-title {
  font-size: 60px;
  margin: 0;
  text-align: center;
}

.pos-title {
  font-size: 30px;
  text-align: center;
  margin-top: 20px;
}

.text-intro-2,
.text-intro-3 {
  display: none;
  text-align: center;
}

#form02 {
  visibility: hidden;
  border: "unset";
  outline: "none";
  stroke: "transparent";
}

.bubble-step2-container {
  opacity: 0;
}

* {
  color: white;
}
</style>
