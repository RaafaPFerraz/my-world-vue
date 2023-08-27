<!--
  Copyright (c) Rafael Padilha Ferraz. All right reserved.
  Licensed under the MIT License. See License.txt in the project root for license information.
-->

<template>
  <div class="container">
    <h1 class="ProjectList__headline">Projects</h1>
    <card-list :items="projects">
      <template #item="{ img, alt, title, description }">
        <div class="ProjectList-card__wrapper">
          <div class="ProjectList-card__heading">
            <img
              :src="img"
              :alt="alt"
              loading="lazy"
              class="Project-card__image" />
          </div>
          <div>
            <h2 class="ProjectList-card__title">{{ title }}</h2>
            <p class="ProjectList-card__description">{{ description }}</p>
            <generic-button
              link-button="https://github.com/RaafaPFerraz/my-world-vue"
              text-button="View Project"
              display="inline-block"
              background-color="#fece2f"
              color="#212227"
              padding="8px 16px"
              border-radius="4px" />
          </div>
        </div>
      </template>
    </card-list>
  </div>
</template>

<script setup>
import CardList from "@/components/CardList.vue";
import GenericButton from "@/components/GenericButton.vue";

import myWorldProject from "@/assets/images/my_world-project.webp";

const projects = [
  {
    img: myWorldProject,
    alt: "My World project image",
    title: "My World",
    description:
      "Development of my first portfolio using the Vue.Js framework.",
  },
];
</script>

<style scoped>
.ProjectList-card__wrapper {
  display: flex;
  flex-direction: column;
  gap: 2rem;
}

@media screen and (min-width: 1024px) {
  .ProjectList-card__wrapper {
    flex-direction: row;
  }

  .ProjectList-card__wrapper div {
    width: 50%;
  }
}

.ProjectList__headline {
  font-size: 1.5rem;
  margin-bottom: 2rem;
}

.ProjectList-card__heading {
  max-width: 500px;
  max-height: 300px;
  margin: 0 auto;
}

.Project-card__image {
  width: 100%;
  height: 100%;
  border-radius: 5px;
}

.ProjectList-card__title {
  font-size: 1.25rem;
  margin-bottom: 1rem;
  font-weight: 500;
}

.ProjectList-card__description {
  margin-bottom: 2rem;
}
</style>
