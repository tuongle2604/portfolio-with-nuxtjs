<template>
  <div class="profile">
    <div class="profile-info">
      <div class="profile-info__image-wrapper">
        <img
          class="profile-info__image"
          src="/avatar-small.jpg"
          alt="avatar"
          srcset="
            /avatar-small.jpg  150w,
            /avatar-medium.jpg 300w,
            /avatar-large.jpg  600w
          "
          sizes="150px"
        />
      </div>
      <h2 class="profile-info__name">Lê Bá Cát Tường</h2>
      <h3 class="profile-info__position">Web Developer</h3>
    </div>
    <div class="profile-social">
      <a
        v-for="item in socialList"
        :key="item.link"
        :href="item.link"
        class="profile-social__link"
        target="_blank"
      >
        <fa :icon="item.icon" class="defaul-icon" />
      </a>
    </div>
    <div class="profile-contact">
      <div
        v-for="item in contactList"
        :key="item.label"
        class="profile-contact__item"
      >
        <span class="profile-contact__label">{{ item.label }}</span>
        <span class="profile-contact__value">{{ item.value }}</span>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      contactList: [
        {
          label: "Date of birth:",
          value: "10/10/1996",
        },
        {
          label: "Phone:",
          value: "0582952221",
        },
        {
          label: "Email:",
          value: "tuongle2604@gmail.com",
        },
        {
          label: "Address:",
          value: "167/3b Bùi Đình Túy, quận Bình Thạnh, TP HCM",
        },
      ],
      socialList: [
        {
          icon: ["fab", "facebook-square"],
          link: "https://www.facebook.com/le.tuong.12177/",
        },
        {
          icon: ["fab", "github-square"],
          link: "https://github.com/tuongle2604",
        },
        {
          icon: ["fab", "linkedin-in"],
          link:
            "https://www.linkedin.com/in/t%C6%B0%E1%BB%9Dng-l%C3%AA-a63bb0167/",
        },
      ],
    };
  },
};
</script>

<style lang="scss">
.profile {
  height: 100%;
}
.profile-info {
  margin-bottom: 1rem;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;

  &__image-wrapper {
    width: 15rem;
    height: 15rem;
    border-radius: 50%;
    margin-bottom: 2rem;
    overflow: hidden;
  }
}
.profile-contact {
  margin-bottom: 2rem;
  &__item {
    display: flex;
    margin-bottom: 1rem;
  }
  &__label {
    flex: 0 0 12rem;
    font-weight: 700;
    color: $secondary-color-dark;
  }
}

.profile-social {
  display: flex;
  justify-content: center;
  margin-bottom: 2rem;
  margin-top: 1rem;
  &__link {
    color: $secondary-color-dark;
    margin: 0 1.5rem;
    &:hover {
      color: $secondary-color;
    }
  }
}
</style>
