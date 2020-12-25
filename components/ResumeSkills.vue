<template>
  <div class="skills">
    <h1 class="skills__title">Skills</h1>
    <ul v-for="skill in skills" :key="skill" class="skills__list">
      <li class="skills__item">{{ skill }}</li>
    </ul>
  </div>
</template>

<script>
export default {
  data() {
    return {
      skills: [
        "Javascript and ES6",
        "Vuejs, Vuex, Vue Router, Nuxt",
        "HTML, CSS and experience with responsive design",
        "Good problem solving skill",
        "Familiar with webpack and its technologies such as bundle, split, HMR, tree shaking, ...",
        "Knowledgeable about web technologies such as SPA, PWA, SSR, Lazy loading, SEO, and optimize performance",
        "Knowledgeable about networking and web security",
        "Knowledgeable about Nodejs, Linux, Nginx and auto deployment with Github",
      ],
    };
  },
};
</script>

<style lang="scss">
.skills {
  &__list {
    padding-left: 0;
    list-style-type: none;
  }
  &__item {
    line-height: 1.8;
    &:before {
      content: "–";
      margin-right: 0.5em;
    }
  }
}
</style>
