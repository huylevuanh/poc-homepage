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
        <img
          v-if="isMobile"
          class="buho-logo-mobile"
          src="~/assets/bg/logo_buho_mobile.png"
          alt="logo"
        />
        <img
          v-else
          class="buho-logo"
          src="~/assets/bg/logo_buho.png"
          alt="logo"
        />
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

if (typeof window !== "undefined") {
  gsap.config({
    trialWarn: false,
  });
  gsap.registerPlugin(ScrollTrigger, MorphSVGPlugin, ScrollSmoother);
}
export default {
  mounted: function () {
    this.scrollAnimation();
    ScrollSmoother.create({
      smooth: 1,
      effects: true,
      ease: "power1.easeInOut",
      smoothTouch: 0.1,
      ignoreMobileResize: true,
    });
  },
  data() {
    return { video: videoBg, isMobile: window.innerWidth <= 768 };
  },
  unmounted: function () {
    ScrollSmoother.get().kill();
  },

  methods: {
    scrollAnimation() {
      const mm = gsap.matchMedia();
      mm.add(
        {
          isDesktop: `(min-width: 769px)`,
          isMobile: `(max-width: 768px)`,
          reduceMotion: "(prefers-reduced-motion: reduce)",
        },
        (context) => {
          const { isDesktop } = context.conditions;

          gsap
            .timeline({
              scrollTrigger: {
                pinType: "transform",
                trigger: ".home-container",
                start: "bottom bottom",
                end: () =>
                  isDesktop
                    ? `${window.innerHeight * 7}`
                    : `${window.innerHeight * 14}`,
                pin: true,
                scrub: 1,
                anticipatePin: 1,
                invalidateOnRefresh: true,
                ease: "expo.out",
              },
            })

            .to(".video-background", {
              filter: "brightness(0.8)",
            })
            .to(
              ".title-container",
              {
                transform: "scale(1.2)",
              },
              "<"
            )
            .to(".video-background", {
              filter: "brightness(0.7)",
            })
            .to(
              ".bubble-step1-container",
              {
                transform: "translate(20%, -40%) rotate(10deg)",
              },
              "-=1"
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
              scale: isDesktop ? "+=2" : 0,
              opacity: 1,
            })
            .to(
              ".bubble-step1-container",
              {
                transform: "translate(-50%, -40%) rotate(0deg)",
                duration: 1,
              },
              "-=1"
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
              scale: isDesktop ? "+=0.5" : 0,
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
            .to(".bubble-step3-container", { scale: 2 })
            .to(
              ".text-intro-2 > span:nth-child(1)",
              { opacity: 1, scale: isDesktop ? "+=2" : "+=0.67" },
              "<"
            )
            .to(".bubble-step3-container", { opacity: 0 })
            .to(".bubble-step4-container", { opacity: 1 }, "<")
            .to(
              ".text-intro-2 > span:nth-child(1)",
              {
                opacity: 0,
                display: "none",
                translateY: -20,
              },
              "+=0.5"
            )
            .to(".text-intro-2 > span:nth-child(2)", {
              display: "block",
              opacity: 1,
              translateY: isDesktop ? -20 : 0,
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
              translateY: isDesktop ? -20 : 0,
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
              display: "flex",
            });
        }
      );
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
  height: 100vh;
  width: 100vw;
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
  display: none;
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
  font-weight: 400;
}

@media screen and (max-width: 768px) {
  .title-container {
    display: flex;
    justify-content: center;
    align-items: center;
    flex-direction: column;
  }

  .title-container > .pos-title {
    font-size: 18px;
    line-height: 28px;
  }
  .text-intro-1,
  .text-intro-2 {
    width: 100%;
  }

  .text-intro-1 > span {
    font-size: 32px;
    opacity: 0;
    overflow: hidden;
    text-overflow: ellipsis;
    white-space: nowrap;
    letter-spacing: -0.35px;
  }

  .text-intro-1 > span:nth-child(2) {
    display: none;
    font-size: 32px;
  }

  .text-intro-1 > span:nth-child(3) {
    display: none;
    font-size: 32px;
  }

  .text-intro-2 > span {
    font-size: 24px;
    opacity: 0;
  }

  .text-intro-2 > span:nth-child(2),
  .text-intro-2 > span:nth-child(3) {
    display: none;
    font-size: 40px;
  }
  .contact-card-container {
    display: none;
  }

  body::-webkit-scrollbar {
    width: 0px;
    background: transparent;
  }
}
</style>
