<template>
  <div class="experience-section">
    <h1 class="experience-section__title">Experience</h1>
    <div class="experience-section__timeline timeline">
      <div v-for="item in timelines" :key="item.date" class="timeline__item">
        <div class="timeline__title">
          <h3 class="timeline__date">{{ item.date }}</h3>
          <p class="timeline__company">{{ item.company }}</p>
        </div>
        <div class="timeline__body">
          <h3 class="timeline__position">{{ item.position }}</h3>
          <ul>
            <li v-for="task in item.tasks" :key="task">{{ task }}</li>
            <li>
              <span class="timeline__techologies">Technologies used:</span>
              {{ item.technologies }}
            </li>
          </ul>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      timelines: [
        {
          date: "10/2018 - 7/2020",
          company: "Sutrix Solution",
          position: "FrontEnd Developer",
          tasks: [
            "Built front end web application base on design",
            "Read and analyze user story",
            "Intergration API with BE team",
            "UAT with QC team",
          ],
          technologies: "Vuejs, Vuex, Vue custom element",
        },
        {
          date: "10/2017 - 10/2018",
          company: "Datamart VietNam",
          position: "Web Developer",
          tasks: [
            "Built front end web application base on design",
            "Maintenance and development API",
            "Work with DA team to build real-time analytics report pages",
          ],
          technologies: "NodeJs, ExpresJs, Mysql, VueJs, SPA",
        },
      ],
    };
  },
};
</script>

<style lang="scss" scoped>
.timeline {
  width: 100%;
  max-width: 80rem;
  background: inherit;
  padding: 10rem 0;
  position: relative;
  &:before {
    content: "";
    position: absolute;
    top: 0px;
    left: 20rem;
    bottom: 0px;
    width: 0.4rem;
    background: $secondary-color-background;
  }
  &:after {
    content: "";
    display: table;
    clear: both;
  }
  &__item {
    display: flex;
    &:not(:last-child) .timeline__body {
      margin: 0 0 4rem;
    }
  }
  &__position {
    margin-bottom: 1rem;
    color: $primary-color-dark;
  }
  &__company {
    color: $primary-color-dark;
  }
  &__techologies {
    color: $primary-color-dark;
  }
  &__title {
    width: 20rem;
    min-width: 20rem;
    margin-bottom: 0.5em;
    padding-right: 3rem;
    text-align: right;
    position: relative;
    &:before {
      content: "";
      position: absolute;
      width: 1rem;
      height: 1rem;
      border: 2px solid $secondary-color;
      background-color: $secondary-color;
      border-radius: 100%;
      top: 1rem;
      right: -0.7rem;
      z-index: 99;
    }
  }
  &__body {
    padding-left: 3rem;
    ul {
      color: #aaa;
      padding-left: 0;
      list-style-type: none;
      li:before {
        content: "–";
        margin-right: 0.5em;
      }
    }
  }
}

@media only screen and (max-width: $screen-small) {
  .timeline {
    padding: 0;
    &::before {
      display: none;
    }
    &__item {
      display: flex;
      flex-direction: column;
    }
    &__title {
      width: 100%;
      text-align: left;
      &::before {
        display: none;
      }
    }
    &__body {
      padding-left: 0;
    }
  }
}
</style>
