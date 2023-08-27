<!--
  Copyright (c) Rafael Padilha Ferraz. All right reserved.
  Licensed under the MIT License. See License.txt in the project root for license information.
-->

<script setup>
import Header from "@/components/layout/Header.vue";
import Footer from "@/components/layout/Footer.vue";
import Landscape from "./Landscape.vue";
import ProjectList from "./ProjectList.vue";
import Skills from "./Skills.vue";
import About from "./About.vue";
import Services from "./Services.vue";
</script>

<template>
  <Header v-once />
  <main>
    <section id="s-landscape">
      <Landscape />
    </section>

    <section id="s-about">
      <About />
    </section>

    <section id="s-services">
      <Services />
    </section>

    <section id="s-skills">
      <Skills />
    </section>

    <section id="s-projects">
      <ProjectList />
    </section>
  </main>

  <Footer v-once />
</template>

<style scoped>
#s-landscape {
  padding: 100px 30px;
}

#s-about,
#s-education,
#s-skills,
#s-projects,
#s-services {
  padding: 30px;
  scroll-margin-top: 50px;
}

@media screen and (min-width: 768px) {
  #s-landscape,
  #s-about,
  #s-education,
  #s-skills,
  #s-projects,
  #s-services {
    padding: 100px 50px;
  }
}
</style>
