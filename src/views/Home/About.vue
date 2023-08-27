<!--
  Copyright (c) Rafael Padilha Ferraz. All right reserved.
  Licensed under the MIT License. See License.txt in the project root for license information.
-->

<template>
  <div class="container">
    <div class="About-card">
      <div class="About-card__wrapper">
        <img
          src="@/assets/images/my_picture.webp"
          alt="A picture of my face"
          class="About-card_image" />
        <article>
          <header class="About-card__heading">
            <span class="About-card__subtitle">About Me</span>
            <h1 class="About-card__title">Rafael Padilha</h1>
          </header>
          <p>
            My name is Rafael Padilha, and I have a degree in Internet Systems
            Technology as well as a technical degree in computer science. I'm
            passionate about Linux and programming, and I'm currently seeking
            opportunities in the Information Technology job market. My goal is
            to develop high-quality applications aimed at streamlining processes
            and reducing costs.
          </p>
        </article>
      </div>
    </div>
  </div>
</template>

<style scoped>
.About-card {
  padding: 2rem;
  border-radius: 5px;
  background-color: var(--color-gunmetal);
}

.About-card__wrapper {
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: 2rem;
}

@media screen and (min-width: 1024px) {
  .About-card__wrapper {
    flex-direction: row;
    align-items: normal;
  }
}

.About-card_image {
  border-radius: 5px;
}

@media screen and (max-width: 425px) {
  .About-card_image {
    width: 100%;
  }
}

.About-card__heading {
  margin-bottom: 1rem;
}

.About-card__subtitle {
  font-size: 1.125rem;
  font-weight: 500;
  color: var(--color-sunglow);
}

.About-card__title {
  font-size: 1.5rem;
}
</style>
