<template>
  <div class="resume">
    <section class="resume__objective">
      <ResumeObjective></ResumeObjective>
    </section>
    <section class="resume__skills">
      <ResumeSkills></ResumeSkills>
    </section>
    <section class="resume__experience">
      <ResumeExperience></ResumeExperience>
    </section>
    <section class="resume__projects">
      <ResumeProjects></ResumeProjects>
    </section>
  </div>
</template>

<script>
import ResumeObjective from "./ResumeObjective";
import ResumeSkills from "./ResumeSkills";
import ResumeExperience from "./ResumeExperience";
import ResumeProjects from "./ResumeProjects";

export default {
  components: {
    ResumeObjective,
    ResumeSkills,
    ResumeExperience,
    ResumeProjects,
  },
};
</script>
<style lang="scss">
.resume section {
  padding: 2rem 2rem 3rem;
  max-width: 90rem;
  background: #222831;
  box-shadow: $box-shadow;

  &:not(:last-child) {
    margin-bottom: $gutter;
  }
}
.resume h1 {
  color: $secondary-color;
  margin-bottom: 1.5rem;
}
@media only screen and (max-width: $screen-small) {
  .resume section {
    &:not(:last-child) {
      margin-bottom: $small-gutter;
    }
  }
}
</style>
