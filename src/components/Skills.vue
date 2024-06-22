<template>
    <div class="window" v-if="isWindowOpen" style="width: 500px">
    <div class="title-bar">
        <div class="title-bar-text">Tools</div>
        <div class="title-bar-controls">
        <button aria-label="Minimize"></button>
        <button aria-label="Maximize"></button>
        <button aria-label="Close" @click="closeWindow"></button>
        </div>
    </div>
    <div class="window-body">
        <div id = 'container'>
            <div id = "sub-container">
              <ul class="tree-view">
                <li>Skill list</li>
                <li>
                  3D Modelling
                  <ul>
                    <li>Blender</li>
                    <li>Spline 3D</li>
                  </ul>
                </li>
                <li>
                  Graphic Design
                  <ul>
                    <li>Adobe Illustrator</li>
                    <li>Adobe Photoshop</li>
                  </ul>
                </li>
                <li>
                  UX/UI Design
                  <ul>
                    <li>Figma</li>
                  </ul>
                </li>
                <li>
                  Front-end Developement
                  <ul>
                    <li>React JS</li>
                    <li>Vue JS</li>
                  </ul>
                </li>
                <li>
                  Back-end Developement and DBMS
                  <ul>
                    <li>Java</li>
                    <li>C++</li>
                    <li>Python</li>
                    <li>Solidity</li>
                    <li>Oracle SQL</li>
                    <li>MongoDB</li>
                  </ul>
                </li>
              </ul>
              <div id = 'icons'>
                <fieldset id = 'col'>
                  <div id = "icon-container">
                    <img src = "@/assets/icons/C.png"/>
                    <p>C++</p>
                  </div>
                  <div id = "icon-container">
                    <img src = "@/assets/icons/python.png"/>
                    <p>Python</p>
                  </div>
                  <div id = "icon-container">
                    <img src = "@/assets/icons/solidity.png"/>
                    <p>Solidity</p>
                  </div>
                </fieldset>
                <fieldset id = 'col'>
                  <div id = "icon-container">
                    <img src = "@/assets/icons/java.png"/>
                    <p>Java</p>
                  </div>
                  <div id = "icon-container">
                    <img src = "@/assets/icons/sql.png"/>
                    <p>SQL</p>
                  </div>
                  <div id = "icon-container">
                    <img src = "@/assets/icons/mongodb.png"/>
                    <p>MongoDB</p>
                  </div>
                </fieldset>
                <fieldset id = 'col'>
                  <div id = "icon-container">
                    <img src = "@/assets/icons/vue.png"/>
                    <p>VueJS</p>
                  </div>
                  <div id = "icon-container">
                    <img src = "@/assets/icons/javascript.png"/>
                    <p>Javascript</p>
                  </div>
                  <div id = "icon-container">
                    <img src = "@/assets/icons/figma.png"/>
                    <p>Figma</p>
                  </div>
                </fieldset>
                <fieldset id = 'col'>
                  <div id = "icon-container">
                    <img src = "@/assets/icons/photoshop.png"/>
                    <p>Photoshop</p>
                  </div>
                  <div id = "icon-container">
                    <img src = "@/assets/icons/illustrator.png"/>
                    <p>Illustrator</p>
                  </div>
                  <div id = "icon-container">
                    <img src = "@/assets/icons/blender.png"/>
                    <p>Blender</p>
                  </div>
                </fieldset>
              </div>
            </div>
        </div>
        <button @click = "closeWindow">OK</button>
    </div>
    </div>
  </template>
  
  <script>
  export default {
    name: 'Skills',
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
  
  .window {
    position: fixed;
    top: 40%;
    left: 2%;
    transform: translate(0%, -50%);
    z-index: 3;

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
    justify-content: flex-start; 
    align-items: center; 
    height: 100%;
    overflow: auto;
}
  
    .window-body button {
      align-self: center; 
      margin-top: 1rem; 
    }
  
    #container {
      padding: 1rem;
      display: flex;
      flex-direction: column; 
      align-items: center; 
    }

    #sub-container {
      max-height: calc(100% - 3rem);
      overflow: auto;
      display: flex;
      gap:1rem;
    }


  
    #about-me {
      display: flex;
      flex-direction: column;
      justify-content: center;
      align-items: center;
    }
  
    #skills {
      display: flex;
      flex-direction: column;
      justify-content: center;
      align-items: center;
    }
  
    #links {
      display: flex;
      flex-direction: column;
      justify-content: center;
      align-items: center;
    }

    #icon-container {
      display: flex;
      flex-direction: column;
      justify-content: space-between; /* This evenly spaces the items */
      align-items: center; /* Center content horizontally */
      text-align: center;
    }

    #col {
      display: flex;
      flex-direction: column;
      justify-content: space-between;
      padding-top: 1rem;
      padding-bottom: 1rem;
}


    #icons {
      display: flex;
      flex-direction: row;
      justify-content: center;
    }
    
  </style>