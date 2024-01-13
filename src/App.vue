<template>
  <div id="app">
    <Skills/>
    <AboutMe/>
    <OpenMe/>
    <MyLinks/>
    <MainPage/>
  </div>
</template>

<script>
import MainPage from '@/components/MainPage.vue';
import AboutMe from '@/components/AboutMe.vue';
import OpenMe from '@/components/OpenMe.vue';
import MyLinks from '@/components/MyLinks.vue';
import Skills from '@/components/Skills.vue';


export default {
  name: 'App',
  components: {
    MainPage,
    AboutMe,
    OpenMe,
    MyLinks,
    Skills,

  }
};
</script>
