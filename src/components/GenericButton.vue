<!--
  Copyright (c) Rafael Padilha Ferraz. All right reserved.
  Licensed under the MIT License. See License.txt in the project root for license information.
-->

<template>
  <a
    :href="linkButton"
    :style="{
      display,
      backgroundColor,
      color,
      fontWeight,
      padding,
      borderRadius,
    }"
    target="_blank"
    rel="noopener"
    class="button">
    {{ textButton }}
  </a>
</template>

<script setup>
const props = defineProps({
  linkButton: {
    type: String,
    default: "#",
  },
  textButton: {
    type: String,
    default: "Button",
  },
  display: {
    type: String,
    default: "block",
  },
  backgroundColor: {
    type: String,
    default: "#FFFFFF",
  },
  color: {
    type: String,
    default: "#000000",
  },
  fontWeight: {
    type: String,
    default: "normal",
  },
  padding: {
    type: String,
    default: "0px",
  },
  borderRadius: {
    type: String,
    default: "0px",
  },
});
</script>

<style scoped>
.button:hover {
  opacity: 0.8;
}
</style>
