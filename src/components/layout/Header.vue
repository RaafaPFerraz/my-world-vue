<!--
  Copyright (c) Rafael Padilha Ferraz. All right reserved.
  Licensed under the MIT License. See License.txt in the project root for license information.
-->

<template>
  <header>
    <div class="container">
      <div class="header-content">
        <h1 class="Header__logo">My World</h1>
        <nav :class="{ 'nav-slide-up': state.displayMenu }">
          <generic-list :items="menuLinks">
            <template #item="{ name, url }">
              <a :href="url" @click="closeMobileMenu">{{ name }}</a>
            </template>
          </generic-list>
        </nav>
        <div
          class="burger-menu"
          @click="openMobileMenu"
          :class="{ 'burger-menu-close-lines': state.showCloseIcon }">
          <span class="line"></span>
          <span class="line"></span>
          <span class="line"></span>
        </div>
      </div>
    </div>
  </header>
  <div v-if="state.showDarkOverlay" class="dark-overlay"></div>
</template>

<script setup>
import { reactive } from "vue";
import GenericList from "@/components/GenericList.vue";

const menuLinks = [
  { name: "Home", url: "#s-landscape" },
  { name: "About Me", url: "#s-about" },
  { name: "Services", url: "#s-services" },
  { name: "Skills", url: "#s-skills" },
  { name: "Projects", url: "#s-projects" },
];

const state = reactive({
  displayMenu: false,
  showCloseIcon: false,
  showDarkOverlay: false,
});

/**
 * Toggles the display of the mobile menu.
 *
 * @author Rafael Padilha
 * @return void
 */
function openMobileMenu() {
  state.displayMenu = !state.displayMenu;
  state.showCloseIcon = !state.showCloseIcon;
  state.showDarkOverlay = !state.showDarkOverlay;

  if (state.displayMenu) {
    document.body.classList.add("no-scroll");
  } else {
    document.body.classList.remove("no-scroll");
  }
}

/**
 * Closes the mobile menu.
 *
 * @author Rafael Padilha
 * @return void
 */
function closeMobileMenu() {
  state.displayMenu = false;
  state.showCloseIcon = false;
  state.showDarkOverlay = false;

  document.body.classList.remove("no-scroll");
}
</script>

<style scoped>
.Header__logo {
  font-weight: 100;
  font-size: 1.25rem;
  text-transform: uppercase;
}

header {
  position: fixed;
  width: 100%;
  padding: 0 30px;
  color: var(--color-white);
  background-color: var(--color-dark-jungle-green);
  z-index: 1;
}

h1 {
  margin: 0;
}

nav {
  position: fixed;
  bottom: 0;
  left: 0;
  width: 100%;
  background-color: var(--color-dark-jungle-green);
  text-align: center;
  height: 70%;
  padding: 30px;
  transform: translateY(100%);
  transition: transform 0.3s ease;
  border-radius: 20px 20px 0 0;
  overflow: auto;
}

.header-content {
  height: 50px;
  display: flex;
  flex-direction: row;
  align-items: center;
  justify-content: space-between;
}

.nav-slide-up {
  transform: translateY(0);
}

nav ul {
  display: flex;
  flex-direction: column;
  gap: 32px;
}

.burger-menu {
  height: 24px;
  width: 26px;
  display: flex;
  flex-direction: column;
  justify-content: space-between;
  align-items: end;
}

.line {
  width: 100%;
  height: 3px;
  border-radius: 5px;
  background-color: var(--color-white);
}

.burger-menu-close-lines .line:nth-child(1) {
  transform: rotate(45deg) translate(4px, 12px);
}

.burger-menu-close-lines .line:nth-child(2) {
  opacity: 0;
}

.burger-menu-close-lines .line:nth-child(3) {
  transform-origin: center;
  transform: rotate(-45deg) translate(4px, -11px);
}

.burger-menu-close-lines .line {
  transition: all 0.3s ease-in-out;
}

.dark-overlay {
  position: fixed;
  top: 0;
  right: 0;
  bottom: 0;
  left: 0;
  background-color: rgba(0, 0, 0, 0.8);
}

@media screen and (min-width: 768px) {
  header {
    padding: 0 50px;
  }
}

@media screen and (min-width: 1024px) {
  nav {
    display: flex;
    justify-content: flex-end;
    align-items: center;
    overflow: visible;
    border-radius: 0;
    transform: none;
    position: static;
    width: auto;
    height: auto;
    padding: 0;
    background-color: transparent;
    text-align: start;
    transition: none;
  }

  nav ul {
    flex-direction: row;
  }

  .burger-menu {
    display: none;
  }
}
</style>
