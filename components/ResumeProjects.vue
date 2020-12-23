<template>
  <div class="projects-section">
    <h1 class="projects-section__title">My Projects</h1>
    <div class="projects-section__list">
      <div
        v-for="project in projects"
        :key="project.name"
        class="project-section__project project"
      >
        <a
          class="project__image-wrapper"
          :href="project.website.link"
          target="_blank"
        >
          <img
            :src="project.image.src"
            :alt="project.image.alt"
            :srcset="project.image.srcset"
            :sizes="project.image.sizes"
            loading="lazy"
          />
        </a>
        <div class="project__info">
          <h2 class="project__name">{{ project.name }}</h2>
          <p class="project__description">
            {{ project.descriptions }}
          </p>
          <div class="project__technologies-used">
            <p class="project__technologies-used--label">Used Stack:</p>
            <ul class="project__technologies-used--list">
              <li
                v-for="technology in project.technologies"
                :key="technology"
                class="project__technologies-used--item"
              >
                {{ technology }}
              </li>
            </ul>
          </div>
          <div class="project__website">
            <fa
              class="defaul-icon project__website-icon"
              :icon="project.website.icon"
            />
            <a
              class="project__website-link"
              :href="project.website.link"
              target="_blank"
            >
              {{ project.website.text }}
            </a>
          </div>
          <div class="project__github">
            <fa
              class="defaul-icon project__github-icon"
              :icon="project.github.icon"
            />
            <a
              class="project__github-link"
              :href="project.github.link"
              target="_blank"
            >
              {{ project.github.text }}
            </a>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      projects: [
        {
          name: "2048",
          descriptions:
            "2048 game with dark theme, can be installed and played offline.",
          technologies: ["Vuejs", "PWA", "Html", "Css"],
          image: {
            src: "/2048-small.png",
            srcset:
              "2048-small.jpg 500w, 2048-medium.jpg 800w, 2048-large.jpg 1200w",
            sizes: "400px, (max-width: 1200px) 500px, (max-width: 600) 100vw",
            alt: "2048 Game",
          },
          website: {
            link: "https://tuongle.xyz/2048/",
            text: "https://tuongle.xyz/2048",
            icon: ["fas", "globe"],
          },
          github: {
            link: "https://github.com/tuongle2604/vue-with-webpack",
            text: "https://github.com/tuongle2604/vue-with-webpack",
            icon: ["fab", "github-square"],
          },
        },
        {
          name: "Realworld vuejs",
          descriptions:
            "It's a realworld blogging, used for learning new framework or programing language instead of todo project.",
          technologies: ["Vuejs", "Html", "Css"],
          image: {
            src: "/realworld-vuejs-small.jpg",
            srcset:
              "realworld-vuejs-small.jpg 500w, realworld-vuejs-medium.jpg 800w, realworld-vuejs-large.jpg 1200w",
            sizes: "400px, (max-width: 1200px) 500px, (max-width: 600) 100vw",
            alt: "Realworld Vuejs",
          },
          website: {
            link: "https://tuongle.xyz/realworld/",
            text: "https://tuongle.xyz/realworld",
            icon: ["fas", "globe"],
          },
          github: {
            link: "https://github.com/tuongle2604/real-world-vuejs",
            text: "https://github.com/tuongle2604/real-world-vuejs",
            icon: ["fab", "github-square"],
          },
        },
      ],
    };
  },
};
</script>

<style lang="scss">
.projects-section {
  &__list {
    margin-top: 2rem;
  }
}
.project {
  display: flex;
  padding-top: 3rem;
  margin-top: 3rem;
  border-top: 1px solid $primary-color;
  &__name {
    color: $primary-color-dark;
    margin-bottom: 1rem;
  }
  &__image-wrapper {
    flex: 0 0 40rem;
    margin-right: 1rem;
    cursor: pointer;
    &:hover {
      opacity: 0.7;
    }
  }
  &__info {
    padding: 0 2rem;
  }
  &__technologies-used {
    color: $primary-color;
    &--label {
      margin-bottom: 1.5rem;
      margin-top: 1.5rem;
    }
    &--list {
      display: flex;
      flex-wrap: wrap;
    }
    &--item {
      padding: 0.5rem 1.3rem;
      border-radius: 1rem;
      margin-right: 1rem;
      margin-bottom: 1rem;
      font-size: 1.3rem;
      background: $secondary-color-background;
      color: $secondary-color;
      cursor: context-menu;
      text-transform: uppercase;
    }
  }
  &__website,
  &__github {
    margin-top: 2rem;
    color: inherit;
    position: relative;
    display: flex;
  }
  &__website-icon,
  &__github-icon {
    position: absolute;
    color: $secondary-color;
  }
  &__website-link,
  &__github-link {
    margin-left: 4rem;
    color: inherit;
    word-break: break-all;
    &:hover {
      color: $primary-color-dark;
    }
  }
}
@media only screen and (max-width: $screen-large) {
  .project {
    flex-direction: column;
    &__image-wrapper {
      flex: 1 1 auto;
      max-width: 50rem;
      margin-right: 0;
      margin-bottom: 2rem;
    }
    &__info {
      padding: 0;
    }
  }
}
</style>
