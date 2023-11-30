<template>
  <svg
    width="720"
    height="720"
    viewBox="0 0 720 720"
    fill="none"
    xmlns="http://www.w3.org/2000/svg"
    class="bubble-step-4"
  >
    <g filter="url(#filter0_ii_145_879)">
      <circle cx="360" cy="360" r="360" fill="black" fill-opacity="0.12" />
    </g>
    <circle
      cx="360"
      cy="360"
      r="359.5"
      stroke="url(#paint0_radial_145_879)"
      style="mix-blend-mode: overlay"
    />
    <defs>
      <filter
        id="filter0_ii_145_879"
        x="-8"
        y="-40"
        width="764.378"
        height="768"
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
        <feOffset dx="36.3779" dy="-40" />
        <feGaussianBlur stdDeviation="32" />
        <feComposite in2="hardAlpha" operator="arithmetic" k2="-1" k3="1" />
        <feColorMatrix
          type="matrix"
          values="0 0 0 0 0.197917 0 0 0 0 0.334659 0 0 0 0 0.95 0 0 0 1 0"
        />
        <feBlend
          mode="normal"
          in2="shape"
          result="effect1_innerShadow_145_879"
        />
        <feColorMatrix
          in="SourceAlpha"
          type="matrix"
          values="0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 127 0"
          result="hardAlpha"
        />
        <feOffset dx="-8" dy="8" />
        <feGaussianBlur stdDeviation="20" />
        <feComposite in2="hardAlpha" operator="arithmetic" k2="-1" k3="1" />
        <feColorMatrix
          type="matrix"
          values="0 0 0 0 0.141176 0 0 0 0 1 0 0 0 0 1 0 0 0 1 0"
        />
        <feBlend
          mode="normal"
          in2="effect1_innerShadow_145_879"
          result="effect2_innerShadow_145_879"
        />
      </filter>
      <radialGradient
        id="paint0_radial_145_879"
        cx="0"
        cy="0"
        r="1"
        gradientUnits="userSpaceOnUse"
        gradientTransform="translate(171.556 729.07) rotate(-58.4362) scale(788.846 473.425)"
      >
        <stop stop-color="white" stop-opacity="0.72" />
        <stop offset="1" stop-color="white" stop-opacity="0" />
      </radialGradient>
    </defs>
  </svg>
</template>

<style>
@media screen and (max-width: 768px) {
  .bubble-step-4 {
    width: 300px;
    height: 300px;
  }
}
</style>
