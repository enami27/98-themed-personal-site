<template>
  <div id="page">
    <div id="main-container" @dblclick="openWindow">
      <img src="@/assets/icons/docs.png" alt="Open Me" />
      <span>open me</span>
    </div>
    <Skills v-if="isSkillsOpen" :isWindowOpen="isSkillsOpen" @closeWindow="closeSkills" />
    <AboutMe v-if="isAboutMeOpen" :isWindowOpen="isAboutMeOpen" @closeWindow="closeAboutMe" />
    <MyLinks v-if="isMyLinksOpen" :isWindowOpen="isMyLinksOpen" @closeWindow="closeMyLinks" />
    <OpenMe :isWindowOpen="isWindowOpen" @closeWindow="closeWindow" @openAboutMe="openAboutMe" @openSkills="openSkills" @openMyLinks="openMyLinks"/>
  </div>
</template>

<script>
import OpenMe from './OpenMe.vue';
import AboutMe from './AboutMe.vue';
import Skills from './Skills.vue';
import MyLinks from './MyLinks.vue';

export default {
  name: 'MainPage',
  components: {
    OpenMe,
    AboutMe,
    Skills,
    MyLinks,
  },
  data() {
    return {
      isWindowOpen: false,
      isAboutMeOpen: false,
      isSkillsOpen: false,
      isMyLinksOpen: false,
    };
  },
  methods: {
    openWindow() {
      this.isWindowOpen = true;
    },
    closeWindow() {
      this.isWindowOpen = false;
    },
    openAboutMe() {
      this.isAboutMeOpen = true;
    },
    closeAboutMe() {
      this.isAboutMeOpen = false;
    },

    openSkills() {
      this.isSkillsOpen = true;
    },

    closeSkills() {
      this.isSkillsOpen = false;
    },

    openMyLinks() {
      this.isMyLinksOpen = true;
    },

    closeMyLinks() {
      this.isMyLinksOpen = false;
    },


  },
};
</script>

<style scoped>
#page {
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
}

#main-container {
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  z-index: 1;
  cursor: pointer;
}

#main-container span {
  margin-top: 10px;
  color: white;
  font-size: 16px;
  text-align: center;
  font-family: 'MS', monospace;
}
</style>
