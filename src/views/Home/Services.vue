<!--
  Copyright (c) Rafael Padilha Ferraz. All right reserved.
  Licensed under the MIT License. See License.txt in the project root for license information.
-->

<template>
  <div class="container">
    <h1 class="Services__headline">Services</h1>
    <card-list :items="services" direction="row">
      <template #item="{ img, alt, title, description }">
        <div class="test">
          <img
            :src="img"
            :alt="alt"
            loading="lazy"
            class="Services-card__image" />
        </div>
        <h2 class="Services-card__title">{{ title }}</h2>
        <p>{{ description }}</p>
      </template>
    </card-list>
  </div>
</template>

<script setup>
import CardList from "@/components/CardList.vue";

import programmingIcon from "@/assets/images/icons/service-programming-icon.svg";
import designIcon from "@/assets/images/icons/service-design-icon.svg";
import projectIcon from "@/assets/images/icons/service-project-icon.svg";

const services = [
  {
    img: programmingIcon,
    alt: "Minimalist icon of a terminal",
    title: "Programming",
    description: "Acting from the initial front-end concepts to the back-end.",
  },
  {
    img: designIcon,
    alt: "Minimalist icon of a color palette",
    title: "UI / UX Design",
    description: "Creativity in the development of modern interfaces.",
  },
  {
    img: projectIcon,
    alt: "Minimalist checklist icon",
    title: "Projects",
    description: "Organization and planning during system project.",
  },
];
</script>

<style scoped>
.test {
  max-width: 64px;
  margin-bottom: 2rem;
}

.Services__headline {
  font-size: 1.5rem;
  margin-bottom: 2rem;
}

.Services-card__image {
  height: 100%;
  width: 100%;
}

.Services-card__title {
  margin-bottom: 1rem;
  font-weight: 500;
}
</style>
