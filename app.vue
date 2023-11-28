<template>
  <div class="home-container">
    <video autoplay muted loop class="video-background">
      <source :src="video" type="video/mp4" />
    </video>
    <img
      src="~/assets/bg/noise-image.png"
      alt="noise-image"
      class="mask-image"
    />
    <BubbleStep1 class="bubble-step1-container" />
    <BubbleStep2 class="bubble-step2-container" />
    <BubbleStep3 class="bubble-step3-container" />
    <BubbleStep4 class="bubble-step4-container" />
    <BubbleStep5 class="bubble-step5-container" />

    <BubbleStep6 class="bubble-step6-container" />

    <ContactCard class="contact-card-container" />

    <div>
      <div class="title-container">
        <img class="buho-logo" src="~/assets/bg/logo_buho.png" alt="logo" />
        <h6 class="pos-title">Desliza para Descubrir</h6>
      </div>
    </div>
    <div class="text-intro-1">
      <span> Te ayudamos a crecer. </span>
      <span>
        Con todo tipo de<br />
        soluciones tecnológicas.
      </span>
      <span>
        Para todo tipo de<br />
        negocios.
      </span>
    </div>

    <div class="text-intro-2">
      <span>Pequeños.</span>
      <span>Y grandes.</span>
      <span
        >A un costo <br />
        asequible.</span
      >
    </div>
  </div>
</template>

<script>
import { MorphSVGPlugin } from "gsap-trial/MorphSVGPlugin";
import { gsap } from "gsap-trial";
import { ScrollSmoother } from "gsap-trial/ScrollSmoother";
import { ScrollTrigger } from "gsap-trial/ScrollTrigger";
import videoBg from "~/assets/bg/background.mp4";
gsap.registerPlugin(ScrollTrigger, MorphSVGPlugin, ScrollSmoother);

export default {
  mounted: function () {
    this.scrollAnimation();
  },
  data() {
    return { video: videoBg };
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
            end: `${window.innerHeight * 10}`,
            pin: true,
            scrub: 1,
            anticipatePin: true,
            invalidateOnRefresh: true,
          },
        })

        .to(
          ".title-container",
          {
            transform: "scale(1.1)",
          },
          "<"
        )
        .to(".video-background", {
          filter: "brightness(0.8)",
        })
        .to(".title-container", {
          transform: "scale(1.2)",
        })
        .to(".video-background", {
          filter: "brightness(0.7)",
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
        .fromTo(
          ".text-intro-1 > span:nth-child(1)",
          { opacity: 0 },
          { opacity: 0.2 }
        )
        .to(".text-intro-1 > span:nth-child(1)", {
          fontSize: 96,
          opacity: 1,
        })
        .to(
          ".bubble-step1-container",
          {
            transform: "translate(-50%, -40%) rotate(0deg)",
            duration: 1,
          },
          "<"
        )
        .to(".text-intro-1 > span:nth-child(1)", {
          opacity: 0,
          display: "none",
          translateY: -20,
        })
        .to(".text-intro-1 > span:nth-child(2)", {
          display: "block",
          opacity: 1,
          translateY: -20,
        })
        .to(".text-intro-1 > span:nth-child(2)", {
          display: "none",
          opacity: 0,
        })
        .to(".text-intro-1 > span:nth-child(3)", {
          display: "block",
          opacity: 1,
          translateY: -20,
          fontSize: 96,
        })

        .to(".bubble-step1-container", {
          opacity: 0,
        })
        .to(
          ".bubble-step2-container",
          {
            opacity: 1,
          },
          "<"
        )

        .to(".video-background", {
          filter: "brightness(0.6)",
        })
        .to(".bubble-step2-container", {
          opacity: 0,
        })
        .to(
          ".text-intro-1 > span:nth-child(3)",
          {
            opacity: 0,
            display: "none",
          },
          "<"
        )
        .to(".mask-image", {
          opacity: 1,
        })
        .to(
          ".video-background",
          {
            filter: "brightness(0.3)",
          },
          "<"
        )
        .to(
          ".bubble-step3-container",
          {
            opacity: 1,
          },
          "<"
        )
        .fromTo(
          ".text-intro-2 > span:nth-child(1)",
          { opacity: 0 },
          { opacity: 0.2 }
        )
        .to(".bubble-step3-container", { scale: 1.3 })
        .to(
          ".text-intro-2 > span:nth-child(1)",
          { opacity: 0.5, scale: "+=1" },
          "<"
        )
        .to(".bubble-step3-container", { scale: 2 })
        .to(
          ".text-intro-2 > span:nth-child(1)",
          { opacity: 1, scale: "+=1.5" },
          "<"
        )
        .to(".bubble-step3-container", { opacity: 0 })
        .to(".bubble-step4-container", { opacity: 1 }, "<")
        .to(".text-intro-2 > span:nth-child(1)", {
          opacity: 0,
          display: "none",
          translateY: -20,
        })
        .to(".text-intro-2 > span:nth-child(2)", {
          display: "block",
          opacity: 1,
          translateY: -20,
        })
        .to(".bubble-step4-container", { opacity: 0 })
        .to(".bubble-step5-container", { opacity: 1 }, "<")
        .to(".text-intro-2 > span:nth-child(2)", {
          display: "none",
          opacity: 0,
        })
        .to(".text-intro-2 > span:nth-child(3)", {
          display: "block",
          opacity: 1,
          translateY: -20,
        })
        .to(".bubble-step5-container", {
          opacity: 0,
        })
        .to(
          ".text-intro-2 > span:nth-child(3)",
          {
            opacity: 0,
          },
          "<"
        )
        .to(".bubble-step6-container", {
          opacity: 1,
        })
        .to(".bubble-step6-container", {
          duration: 0.5,
          opacity: 0,
        })
        .to(".contact-card-container", {
          opacity: 1,
        });
    },
  },
};
</script>

<style>
.home-container {
  display: flex;
  position: relative;
  justify-content: center;
  align-items: center;
  will-change: transform;
  height: 100vh;
}

.video-background {
  position: absolute;
  top: 0;
  left: 0;
  height: 100vh;
  width: 100vw;
  object-fit: cover;

  filter: brightness(100%);
}

.mask-image {
  position: absolute;
  top: 0;
  left: 0;
  height: 100vh;
  width: 100vw;
  opacity: 0;
}

.bubble-step1-container,
.bubble-step2-container,
.bubble-step3-container,
.bubble-step4-container,
.bubble-step5-container,
.bubble-step6-container {
  position: absolute;
  top: 50%;
  left: 50%;
}

.contact-card-container {
  opacity: 0;
}

.bubble-step1-container {
  transform: translate(60%, -90%);
}

.bubble-step6-container {
  transform: translate(-40%, -50%);
  opacity: 0;
}

.bubble-step2-container,
.bubble-step3-container,
.bubble-step4-container,
.bubble-step5-container {
  transform: translate(-50%, -50%);
  opacity: 0;
}

.pos-title {
  font-size: 30px;
  text-align: center;
  margin-top: 20px;
}

.text-intro-2,
.text-intro-1 {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  position: absolute;
  text-align: center;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
}

.text-intro-1 > span {
  font-size: 32px;
  opacity: 0;
}

.text-intro-1 > span:nth-child(2) {
  display: none;
  font-size: 96px;
}

.text-intro-1 > span:nth-child(3) {
  display: none;
  font-size: 64px;
}

.text-intro-2 > span {
  font-size: 32px;
  opacity: 0;
}

.text-intro-2 > span:nth-child(2),
.text-intro-2 > span:nth-child(3) {
  display: none;
  font-size: 96px;
}

* {
  color: white;
}
</style>
