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
    <div class="window" id = "taskbar">
        <button @click="openWindow">
            <img src="@/assets/icons/start.png" alt="start"/>
            <span>Start</span>
        </button>
        <div class="status-bar">
            <p class="status-bar-field">imane.xyz © 2024</p>
        </div>
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
  top: 70%;
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

#taskbar {
  position: fixed;
  bottom: 0;
  left: 0;
  width: 100%;
  z-index: 1;
  display: flex;
  justify-content: space-between;
}

.status-bar {
    display: flex;
    align-items: center;
    padding-right: 15px;
  }

  .status-bar p {
    padding: 4px;
    font-size: 13px;
  }

  #taskbar button {
    background: none;
    border: none;
    color: black;
    cursor: pointer;
    display:flex;
    justify-content: center;
    align-items: center;
    gap:0.5rem;

  }

  #taskbar button img {
    width: 20px;
    height: 20px;
    padding: 4px
  }

  #taskbar button span {
    font-family: 'MS', monospace;
    font-size: 16px;
    font-weight: bold
  }

</style>
