<template>
  <div class="contact-card">
    <div class="phone-email">
      <span>+503 7260 1693</span>
      <span>hola@buhopay.com↗</span>
    </div>
    <div class="card-footer">
      <span>
        De El Salvador para el mundo con ♥️<br />
        BUHO Holdings, S.A. © 2023. All Rights Reserved
      </span>
      <div class="social-container">
        <IconFaceBook /> <IconLinkedin /> <IconTwitter />
      </div>
    </div>
  </div>
</template>

<style>
.phone-email {
  display: flex;
  flex-direction: column;
  gap: 22px;
  font-size: 96px;
}
.card-footer {
  display: flex;
  justify-content: space-between;
}

.social-container {
  display: flex;
  gap: 20px;
}

.contact-card {
  border-radius: 40px;
  background: transparent;
  display: flex;
  flex-direction: column;
  justify-content: space-between;

  width: 1504px;
  height: 682px;
  border: solid 2px transparent;
  border: 1px solid rgba(165, 162, 162, 0.495);
  padding: 80px;

  filter: brightness(120%);

  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);

  box-shadow: rgba(0, 0, 0, 0.25) 0px 54px 55px,
    rgba(0, 0, 0, 0.12) 0px -12px 30px, rgba(0, 0, 0, 0.12) 0px 4px 6px,
    rgba(0, 0, 0, 0.17) 0px 12px 13px, rgba(0, 0, 0, 0.09) 0px -3px 5px;
}

@media screen and (max-width: 768px) {
  .contact-card {
    width: 343px;
    height: 480px;
    padding: 64px 0px;
    margin: 0 16px;
    border-radius: 16px;
    transform: none;
    position: unset;
    justify-content: space-between;
    top: unset;
    left: unset;
  }

  .phone-email > span:first-child {
    font-size: 40px;
    line-height: 48px;
  }

  .phone-email > span:last-child {
    font-size: 32px;
    line-height: 48px;
  }

  .phone-email {
    margin: 0 8px;
  }

  .card-footer {
    flex-direction: column;
    gap: 24px;
    margin: 0 8px;
  }

  .card-footer > span {
    font-size: 14px;
    white-space: nowrap;
  }

  .social-container {
    gap: 24px;
  }
}
</style>
