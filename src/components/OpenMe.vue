<template>
  <div class="window" v-if="isWindowOpen" style="width: 300px">
  <div class="title-bar">
      <div class="title-bar-text">Open me</div>
      <div class="title-bar-controls">
      <button aria-label="Minimize"></button>
      <button aria-label="Maximize"></button>
      <button aria-label="Close" @click="closeWindow"></button>
      </div>
  </div>
  <div class="window-body">
      <div id = 'container'>
        <div id = 'about-me'>
          <img src = "@/assets/icons/folder.png" alt = "About me" height="45" @dblclick="openAboutMe"/>
          <p>About me</p>
        </div>
        <div id = 'skills'>
          <img src="@/assets/icons/folder.png" alt='Skills' height="45" @dblclick="openSkills"/>
          <p>Skills</p>
        </div>
        <div id = 'links'>
          <img src = "@/assets/icons/links.png" alt = "Links" height="45" @dblclick="openMyLinks"/>
          <p>Links</p>
        </div>
      </div>
      <button @click = "closeWindow">OK</button>
  </div>
  </div>
</template>

<script>
export default {
  name: 'OpenMe',
  props: {
    isWindowOpen: Boolean,
  },
  methods: {
    closeWindow() {
      this.$emit('closeWindow');
    },

    openAboutMe() {
      this.$emit('openAboutMe');
    },

    openSkills() {
      this.$emit('openSkills');
    },

    openMyLinks() {
      this.$emit('openMyLinks');
    },
  },
};
</script>

<style scoped>
.window {
  position: fixed;
  top: 50%;
  left: 50%;
  transform: translate(-30%, -50%);
  z-index: 2;

  @media screen and (max-width: 768px) {
    width: 90%;
    max-width: 500px; 
    transform: translate(-50%, -50%);
    left: 50%;
  }

  @media screen and (min-width: 769px) and (max-width: 1024px) {
    width: 90%;
    max-width: 500px; 
    transform: translate(-50%, -50%);
    left: 50%;
  }
}

.window-body {
  display: flex;
  flex-direction: column;
  justify-content: space-between;
  height: 10rem;
}

.window-body button {
  align-self: center;
  margin-top: 1rem;
}

#container {
  padding: 1rem;
  display: flex;
  flex-direction: row;
  gap: 2rem;
}

#about-me,
#skills,
#links {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  cursor: pointer;
}
</style>