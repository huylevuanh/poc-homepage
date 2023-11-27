<template>
  <svg
    width="864"
    height="864"
    viewBox="0 0 864 864"
    fill="none"
    xmlns="http://www.w3.org/2000/svg"
  >
    <g filter="url(#filter0_ii_1271_11435)">
      <path
        d="M661.945 88.2571C786.902 201.196 778.038 388.88 709.393 542.632C644.391 688.222 509.923 797.209 350.835 785.078C184.977 772.431 47.4616 651.263 10.0809 489.307C-27.6496 325.837 42.6413 157.185 185.61 69.2249C335.207 -22.8125 531.658 -29.4995 661.945 88.2571Z"
        fill="black"
        fill-opacity="0.48"
        id="form03"
      />
    </g>
    <defs>
      <filter
        id="filter0_ii_1271_11435"
        x="-10"
        y="-40"
        width="829"
        height="836"
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
        <feOffset dx="60" dy="-40" />
        <feGaussianBlur stdDeviation="48" />
        <feComposite in2="hardAlpha" operator="arithmetic" k2="-1" k3="1" />
        <feColorMatrix
          type="matrix"
          values="0 0 0 0 1 0 0 0 0 0.48 0 0 0 0 0 0 0 0 0.8 0"
        />
        <feBlend
          mode="normal"
          in2="shape"
          result="effect1_innerShadow_1271_11435"
        />
        <feColorMatrix
          in="SourceAlpha"
          type="matrix"
          values="0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 127 0"
          result="hardAlpha"
        />
        <feOffset dx="-10" dy="10" />
        <feGaussianBlur stdDeviation="30" />
        <feComposite in2="hardAlpha" operator="arithmetic" k2="-1" k3="1" />
        <feColorMatrix
          type="matrix"
          values="0 0 0 0 0 0 0 0 0 1 0 0 0 0 1 0 0 0 0.64 0"
        />
        <feBlend
          mode="normal"
          in2="effect1_innerShadow_1271_11435"
          result="effect2_innerShadow_1271_11435"
        />
      </filter>
    </defs>

    <g filter="url(#filter0_ii_1271_11424)">
      <path
        d="M432 864C670.587 864 864 670.587 864 432C864 193.413 670.587 0 432 0C193.413 0 0 193.413 0 432C0 670.587 193.413 864 432 864Z"
        fill="black"
        fill-opacity="0.48"
        id="form04"
      />
    </g>
    <defs>
      <filter
        id="filter0_ii_1271_11424"
        x="-10"
        y="-40"
        width="934"
        height="914"
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
        <feOffset dx="60" dy="-40" />
        <feGaussianBlur stdDeviation="48" />
        <feComposite in2="hardAlpha" operator="arithmetic" k2="-1" k3="1" />
        <feColorMatrix
          type="matrix"
          values="0 0 0 0 1 0 0 0 0 0.48 0 0 0 0 0 0 0 0 0.8 0"
        />
        <feBlend
          mode="normal"
          in2="shape"
          result="effect1_innerShadow_1271_11424"
        />
        <feColorMatrix
          in="SourceAlpha"
          type="matrix"
          values="0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 127 0"
          result="hardAlpha"
        />
        <feOffset dx="-10" dy="10" />
        <feGaussianBlur stdDeviation="30" />
        <feComposite in2="hardAlpha" operator="arithmetic" k2="-1" k3="1" />
        <feColorMatrix
          type="matrix"
          values="0 0 0 0 0 0 0 0 0 1 0 0 0 0 1 0 0 0 0.64 0"
        />
        <feBlend
          mode="normal"
          in2="effect1_innerShadow_1271_11424"
          result="effect2_innerShadow_1271_11424"
        />
      </filter>
    </defs>
  </svg>
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
      gsap.to("#form04", {
        morphSVG: "#form03",
        ease: "sine.easeInOut",
        duration: 2,
        repeat: -1,
        yoyo: true,
      });
    },
  },
};
</script>

<style>
svg {
  outline: none;
  border: unset;
  stroke-width: 0;
  background: transparent;
}
#form03 {
  visibility: hidden;
}
</style>
