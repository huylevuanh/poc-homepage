<template>
  <div class="step-6-container">
    <div class="bubble-1">
      <BubbleStep3 class="bubble" />
      <div class="text-description">
        <span
          >Análisis de <br />
          datos</span
        >
        <ArrowRight />
      </div>
    </div>

    <div class="bubble-2">
      <BubbleStep4 class="bubble" />
      <div class="text-description">
        <span
          >Procesamiento de <br />
          órdenes</span
        >
        <ArrowRight />
      </div>
    </div>

    <div class="bubble-3">
      <svg
        width="368"
        height="368"
        viewBox="0 0 368 368"
        fill="none"
        xmlns="http://www.w3.org/2000/svg"
        class="bubble"
      >
        <g filter="url(#filter0_ii_145_1112)">
          <circle cx="183" cy="183" r="183" fill="black" fill-opacity="0.48" />
        </g>
        <circle
          cx="183"
          cy="183"
          r="182.5"
          stroke="url(#paint0_radial_145_1112)"
          style="mix-blend-mode: overlay"
        />
        <defs>
          <filter
            id="filter0_ii_145_1112"
            x="-4"
            y="-16"
            width="386"
            height="386"
            filterUnits="userSpaceOnUse"
            color-interpolation-filters="sRGB"
          >
            <feFlood flood-opacity="0" result="BackgroundImageFix" />
            <feBlend
              mode="normal"
              in="SourceGraphic"
              in2="BackgroundImageFix"
              result="shape"
            />
            <feColorMatrix
              in="SourceAlpha"
              type="matrix"
              values="0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 127 0"
              result="hardAlpha"
            />
            <feOffset dx="16" dy="-16" />
            <feGaussianBlur stdDeviation="16" />
            <feComposite in2="hardAlpha" operator="arithmetic" k2="-1" k3="1" />
            <feColorMatrix
              type="matrix"
              values="0 0 0 0 1 0 0 0 0 0.48 0 0 0 0 0 0 0 0 0.5 0"
            />
            <feBlend
              mode="normal"
              in2="shape"
              result="effect1_innerShadow_145_1112"
            />
            <feColorMatrix
              in="SourceAlpha"
              type="matrix"
              values="0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 127 0"
              result="hardAlpha"
            />
            <feOffset dx="-4" dy="4" />
            <feGaussianBlur stdDeviation="12" />
            <feComposite in2="hardAlpha" operator="arithmetic" k2="-1" k3="1" />
            <feColorMatrix
              type="matrix"
              values="0 0 0 0 0 0 0 0 0 1 0 0 0 0 1 0 0 0 0.64 0"
            />
            <feBlend
              mode="normal"
              in2="effect1_innerShadow_145_1112"
              result="effect2_innerShadow_145_1112"
            />
          </filter>
          <radialGradient
            id="paint0_radial_145_1112"
            cx="0"
            cy="0"
            r="1"
            gradientUnits="userSpaceOnUse"
            gradientTransform="translate(56.4257 313.777) rotate(-50.0865) scale(384.824 366.385)"
          >
            <stop stop-color="white" stop-opacity="0.74" />
            <stop offset="1" stop-color="white" stop-opacity="0" />
          </radialGradient>
        </defs>
      </svg>

      <div class="text-description">
        <span
          >Sobre<br />
          nosotros</span
        >
        <ArrowRight />
      </div>
    </div>
  </div>
</template>

<script>
import { MorphSVGPlugin } from "gsap-trial/MorphSVGPlugin";
import { gsap } from "gsap-trial";

gsap.registerPlugin(MorphSVGPlugin);

export default {
  mounted: function () {
    this.distort();
  },
  methods: {
    distort() {
      const mm = gsap.matchMedia();

      gsap.to(".bubble-1", {
        transform: "translate(-20px, -30px)",
        ease: "sine.easeInOut",
        duration: 1,
        repeat: -1,
        yoyo: true,
      });

      gsap.to(".bubble-2", {
        transform: "translate(30px, -40px)",
        ease: "sine.easeInOut",
        duration: 1,
        repeat: -1,
        yoyo: true,
      });
      gsap.to(".bubble-3", {
        transform: "translate(0px, 30px)",
        ease: "power1.easeInOut",
        duration: 1,
        repeat: -1,
        yoyo: true,
      });
    },
  },
};
</script>

<style>
.step-6-container {
  position: relative;
  width: 50%;
  height: 100%;
}

.bubble-1,
.bubble-2,
.bubble-3 {
  position: absolute;
}

.bubble-1 {
  top: 30.5%;
}

.bubble-1 > .bubble {
  width: 432px;
  height: 432px;
}

.bubble-1 > .text-description {
  position: absolute;
  top: 50%;
  left: 50%;
  width: 100%;
  transform: translate(-50%, -50%);
  display: flex;
  flex-direction: column;
  align-items: center;
  text-align: center;
  font-size: 48px;
}

.bubble-2 {
  top: 15%;
  left: 28%;
}

.bubble-2 > .bubble {
  width: 521px;
  height: 521px;
}

.bubble-2 > .text-description {
  position: absolute;
  top: 50%;
  left: 50%;
  width: 100%;
  transform: translate(-50%, -50%);
  display: flex;
  flex-direction: column;
  align-items: center;
  text-align: center;
  font-size: 48px;
}

.bubble-3 {
  top: 48%;
  left: 25%;
}

.bubble-3 > .text-description {
  position: absolute;
  top: 50%;
  left: 50%;
  width: 100%;
  transform: translate(-50%, -50%);
  display: flex;
  flex-direction: column;
  align-items: center;
  text-align: center;
  font-size: 48px;
}

@media screen and (max-width: 768px) {
  .step-6-container {
    width: 100%;
  }

  .bubble-2 > .bubble {
    width: 240px;
    height: 240px;
  }
  .bubble-1 > .bubble {
    width: 180px;
    height: 180px;
  }
  .bubble-3 > .bubble {
    width: 140px;
    height: 140px;
  }

  .bubble-3 > .text-description,
  .bubble-1 > .text-description,
  .bubble-2 > .text-description {
    font-size: 18px;
    line-height: 28px;
  }

  .bubble-1 {
    top: 50%;
  }
  .bubble-2 {
    top: 25%;
    left: 18%;
  }

  .bubble-3 {
    top: 48%;
    left: 45%;
  }
}
</style>
