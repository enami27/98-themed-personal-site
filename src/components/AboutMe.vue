<template>
    <div class="window" v-if="isWindowOpen" style="width: 300px">
    <div class="title-bar">
        <div class="title-bar-text">About me</div>
        <div class="title-bar-controls">
        <button aria-label="Minimize"></button>
        <button aria-label="Maximize"></button>
        <button aria-label="Close" @click="closeWindow"></button>
        </div>
    </div>
    <div class="window-body">
        <div id = 'container'>
            <img src="@/assets/icons/info.png" alt="About me" />
            <p>Freelance multidisciplinary designer and developer, always keen to learn about new technologies and creating compelling visual experiences ranging from 3D design to UX/UI. Weightlifter and fitness enthusiast.</p> 
        </div>
        <button @click = "closeWindow">OK</button>
    </div>
    </div>
</template>

<script>
  export default {
    name: 'AboutMe',
    props: {
    isWindowOpen: Boolean,
  },

    methods: {
        closeWindow() {
          this.$emit('closeWindow');
        },
    },
  };
</script>
  
<style scoped>
#container {
  justify-content: center;
  align-items: center;
  display: flex;
  gap: 1rem; 
}

.window {
  position: fixed;
  top: 50%;
  left: 50%;
  transform: translate(90%, -90%);
  z-index: 3;

  @media screen and (max-width: 768px) {
    width: 90%;
    max-width: 500px; 
    transform: translate(-50%, 70%);
    left: 50%;
  }

  @media screen and (min-width: 769px) and (max-width: 1024px) {
    width: 90%;
    max-width: 500px; 
    transform: translate(-50%, 70%);
    left: 50%;
  }
}

.window-body {
    text-align: center;
}

</style>