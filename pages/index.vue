<template>
  <div class="container">
    <aside class="aside">
      <SideBar></SideBar>
    </aside>
    <main class="main">
      <MainContent></MainContent>
    </main>
  </div>
</template>

<script>
import SideBar from "@/components/SideBar";
import MainContent from "@/components/MainContent";
export default {
  components: {
    SideBar,
    MainContent,
  },
  head() {
    return {
      title: "Portfolio - TuongLe",
      meta: [
        {
          hid: "Portfolio",
          name: "Portfolio",
          content: "Portfolio with dark theme",
        },
      ],
    };
  },
};
</script>

<style lang="scss">
.container {
  height: 100vh;
  display: flex;
  overflow: hidden;
  background: $primary-color-background;
  color: $primary-color-light;
}

.aside {
  height: 100%;
  flex: 0 0 35rem;
  padding: $gutter 2rem;
  align-self: flex-start;
  color: $secondary-color;
  box-shadow: $box-shadow;
  background-image: $secondary-color-background;
}
.main {
  width: 100%;
  padding: $gutter;
  overflow: auto;
}
::-webkit-scrollbar {
  width: 10px;
}
/* Track */
::-webkit-scrollbar-track {
  box-shadow: inset 0 0 5px $primary-color;
  border-radius: 10px;
}
/* Handle */
::-webkit-scrollbar-thumb {
  background: $primary-color-dark;
  border-radius: 10px;
}
@media only screen and (max-width: $screen-medium) {
  .container {
    height: auto;
    flex-direction: column;
    overflow: visible;
  }
  .aside {
    width: 100%;
    padding: 3rem $gutter;
  }
  .main {
    background: inherit;
    overflow: visible;
  }
}
@media only screen and (max-width: $screen-small) {
  .main {
    padding: $small-gutter;
  }
  .aside {
    padding: $small-gutter;
  }
}
</style>
