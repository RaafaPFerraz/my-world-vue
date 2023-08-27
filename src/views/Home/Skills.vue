<!--
  Copyright (c) Rafael Padilha Ferraz. All right reserved.
  Licensed under the MIT License. See License.txt in the project root for license information.
-->

<template>
  <div class="container">
    <h1 class="Skills__headline">Skills</h1>
    <div class="Skills__wrapper">
      <div class="Skills__content" v-for="skill in skills" :key="skill.name">
        <div class="Skills__name"
          >{{ skill.name }} <span>{{ skill.progress }}</span></div
        >
        <div class="Skills__bar">
          <div
            class="Skills__progress"
            :style="{ width: skill.progress }"></div>
        </div>
      </div>
    </div>
  </div>
</template>

<script setup>
import { reactive } from "vue";

const skills = reactive([
  { name: "HTML5", progress: "90%" },
  { name: "CSS3", progress: "90%" },
  { name: "JavaScript", progress: "40%" },
  { name: "Vue.JS", progress: "40%" },
  { name: "Java", progress: "60%" },
  { name: "Spring", progress: "50%" },
  { name: "Relational Databases", progress: "70%" },
  { name: "Git", progress: "50%" },
]);
</script>

<style scoped>
.Skills__headline {
  font-size: 1.5rem;
  margin-bottom: 2rem;
}

.Skills__wrapper {
  display: flex;
  flex-direction: column;
  flex-wrap: wrap;
  gap: 32px;
}

@media screen and (min-width: 768px) {
  .Skills__wrapper {
    flex-direction: row;
  }
}

@media screen and (min-width: 768px) {
  .Skills__content {
    flex-basis: calc(50% - 32px);
    flex-grow: 1;
  }
}

.Skills__name {
  display: flex;
  flex-direction: row;
  justify-content: space-between;
  margin-bottom: 8px;
}

.Skills__bar {
  height: 10px;
  background-color: var(--color-gunmetal);
  border-radius: 5px;
}

.Skills__progress {
  height: 10px;
  border-radius: 5px;
  background-color: var(--color-sunglow);
}
</style>
