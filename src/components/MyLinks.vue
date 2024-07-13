<template>
    <div class="window" v-if="isWindowOpen" style="width: 300px">
    <div class="title-bar">
        <div class="title-bar-text">My Links</div>
        <div class="title-bar-controls">
        <button aria-label="Minimize"></button>
        <button aria-label="Maximize"></button>
        <button aria-label="Close" @click="closeWindow"></button>
        </div>
    </div>
    <div class="window-body">
        <p>My Links :</p>
        <div id = 'container'>
            <a href = "https://contra.com/imanebe27?utm_campaign=social_sharing&utm_medium=independent_share&utm_source=copy_link" target = "_blank"><button>Portfolio</button></a>
            <a href = "https://github.com/enami27" target = "_blank"><button>Github</button></a>
            <a href="mailto:whoisimane27@gmail.com"><button>E-mail</button></a>
        </div>
        <button @click = "closeWindow">OK</button>
    </div>
    </div>
</template>

<script>
  export default {
    name: 'MyLinks',
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
  margin-bottom: 1rem;
  gap: 1rem; 
}

.window {
  position: fixed;
  top: 50%;
  left: 50%;
  transform: translate(10%, 100%);
  z-index: 3;

  @media screen and (max-width: 768px) {
    width: 90%;
    max-width: 500px; 
    transform: translate(-50%, -200%);
    left: 50%;
  }

  @media screen and (min-width: 769px) and (max-width: 1024px) {
    width: 90%;
    max-width: 500px; 
    transform: translate(-50%, -200%);
    left: 50%;
  }
}
.window-body {
    text-align: center;
}

</style>