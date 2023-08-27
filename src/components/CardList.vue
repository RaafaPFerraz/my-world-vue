<!--
  Copyright (c) Rafael Padilha Ferraz. All right reserved.
  Licensed under the MIT License. See License.txt in the project root for license information.
-->

<template>
  <div
    class="CardList__wrapper"
    :class="['CardList__wrapper', `flex-${direction}`]">
    <article v-for="(item, index) in items" :key="index" class="CardList-card">
      <slot name="item" v-bind="item" />
    </article>
  </div>
</template>

<script setup>
const props = defineProps({
  items: {
    type: Array,
    required: true,
  },
  direction: {
    type: String,
    default: "column",
    validator: (value) => ["row", "column"].includes(value),
  },
});
</script>

<style scoped>
.CardList__wrapper {
  display: flex;
  gap: 2rem;
}

.CardList-card {
  padding: 32px;
  border-radius: 5px;
  flex-grow: 1;
  background-color: var(--color-gunmetal);
  box-shadow: 4px 4px 10px 0px rgba(0, 0, 0, 0.25);
}

.CardList__wrapper.flex-column {
  flex-direction: column;
}

.CardList__wrapper.flex-row {
  flex-direction: row;
  flex-wrap: wrap;
}

@media screen and (min-width: 768px) {
  .CardList__wrapper.flex-row .CardList-card {
    flex-basis: calc(50% - 2rem);
  }
}

@media screen and (min-width: 1024px) {
  .CardList__wrapper.flex-row .CardList-card {
    flex-basis: calc(33% - 2rem);
  }
}
</style>
