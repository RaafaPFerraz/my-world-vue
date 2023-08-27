<!--
  Copyright (c) Rafael Padilha Ferraz. All right reserved.
  Licensed under the MIT License. See License.txt in the project root for license information.
-->

<template>
  <div class="container">
    <div class="Landscape__wrapper">
      <div>
        <img
          src="@/assets/images/landscape-home.svg"
          alt="Developer sitting on a big notebook"
          class="Landscape__image" />
      </div>
      <div class="Landscape__body">
        <h1 class="Landscape__title">
          Developing web systems with
          <span class="text-highlight">excellence</span> and
          <span class="text-highlight">quality</span>.
        </h1>
        <p class="Landscape__subtitle">
          Designing and developing innovative web systems with creativity and a
          keen eye for detail.
        </p>
        <generic-button
          :link-button="Curriculum"
          text-button="Resume"
          display="inline-block"
          background-color="#fece2f"
          color="#212227"
          font-weight="500"
          padding="16px 50px"
          border-radius="50px"
          download />
      </div>
    </div>
  </div>
</template>

<script setup>
import GenericButton from "@/components/GenericButton.vue";
import Curriculum from "@/assets/documents/RafaelPadilhaFerraz.pdf";
</script>

<style scoped>
.Landscape__wrapper {
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: 40px;
}

@media screen and (min-width: 768px) {
  .Landscape__wrapper {
    flex-direction: row-reverse;
    justify-content: space-between;
  }

  .Landscape__wrapper div {
    width: 50%;
  }
}

.Landscape__image {
  width: 100%;
  height: 100%;
}

.Landscape__body {
  text-align: center;
}

@media screen and (min-width: 768px) {
  .Landscape__body {
    text-align: left;
  }
}

.Landscape__title {
  font-size: 2.5rem;
  font-weight: 100;
}

.Landscape__subtitle {
  font-size: 20px;
  margin: 48px 0;
}

.text-highlight {
  color: var(--color-sunglow);
}
</style>
