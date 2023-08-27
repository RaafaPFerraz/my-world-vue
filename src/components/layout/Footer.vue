<!--
  Copyright (c) Rafael Padilha Ferraz. All right reserved.
  Licensed under the MIT License. See License.txt in the project root for license information.
-->

<template>
  <footer class="Footer">
    <div class="Footer__wrapper container">
      <section>
        <h4 class="Footer__heading">Contact</h4>
        <address>
          <a href="mailto:rafaelpadilha.mobile.dev@gmail.com" class="Footer__link">
            rafaelpadilha.mobile.dev@gmail.com
          </a>
        </address>
      </section>
      <section>
        <h4 class="Footer__heading">Social Media</h4>
        <nav>
          <generic-list :items="links">
            <template #item="{ name, url }">
              <a
                :href="url"
                target="_blank"
                rel="noopener"
                class="Footer__link"
                >{{ name }}</a
              >
            </template>
          </generic-list>
        </nav>
      </section>
    </div>
    <p class="Footer__copyright text-center">
      Created by &copy;Rafael Padilha Ferraz
    </p>
  </footer>
</template>

<script setup>
import GenericList from "@/components/GenericList.vue";

const links = [
  { name: "Github", url: "https://github.com/RaafaPFerraz" },
  { name: "LinkedIn", url: "https://www.linkedin.com/in/rafaelpf-dev/" },
];
</script>

<style scoped>
.Footer {
  padding: 30px;
  background-color: var(--color-mist-blue);
}

.Footer__wrapper {
  display: flex;
  flex-direction: column;
  gap: 2rem;
  margin: 24px auto 40px;
}

@media screen and (min-width: 1024px) {
  .Footer__wrapper {
    flex-direction: row;
    align-items: center;
    justify-content: space-between;
  }
}

.Footer__heading {
  margin-bottom: 0.5rem;
}

.Footer__link {
  font-size: 0.9rem;
  color: var(--color-white);
  text-decoration: none;
}

@media screen and (min-width: 1024px) {
  .Footer__link:hover {
    text-decoration: underline;
  }
}

.Footer__list {
  display: flex;
  flex-direction: column;
  gap: 0.5rem;
}

.Footer__copyright {
  font-weight: 500;
  font-size: 0.875rem;
}
</style>
