<template>
<div>
  <div class="projects-wrapper" v-scroll-reveal.reset="{delay: 80}">
    <h3 class="few" v-scroll-reveal.reset="{delay: 60}"><span class="here" id="projects">Here </span>are a few of my projects</h3>
    <div class="project-ml-stack visible" id="p1">
      <!-- <div class="laptop">
        <video loop autoplay class="laptop-screen">

            <source src="../assets/music-lovers.mp4"
                    type="video/mp4">

            Sorry, your browser doesn't support embedded videos.
        </video>
        <img class="laptop-right" src="../assets/mac-laptop.png" alt="laptop screenshot">
      </div> -->
      <img class="laptop-right" src="../assets/developersquiz-laptop.png" alt="laptop screenshot">
      <img class="phone-right" src="../assets/developers-phone.jpg" alt="phone screenshot">
        <div class="tech-stack" id="tech-dq">
        <img class="tech react" src="../assets/react.png" alt="rails logo">
        <img class="tech gql" src="../assets/graphqlPink.png" alt="ruby logo">
        <img class="tech ts" src="../assets/ts.png" alt="postgres logo">
        <img class="tech styled" src="../assets/styledComponentsLogo.png" alt="materialize logo">
      </div>
    </div>
    <div class="project-elm-stack invisible"  id="p2">
      <img class="laptop-right" src="../assets/music-lovers-laptop.png" alt="laptop screenshot">
      <img class="phone-right" src="../assets/music-lovers-phone-smaller.jpg" alt="phone screenshot">
        <div class="tech-stack" id="tech-ml">
        <img class="tech rails" src="../assets/rails.png" alt="rails logo">
        <img class="tech ruby" src="../assets/ruby.png" alt="ruby logo">
        <img class="tech sql" src="../assets/postgresql.png" alt="postgres logo">
        <img class="tech material" src="../assets/materialize.png" alt="materialize logo">
      </div>
      
    </div>
    <div class="project-coffee-stack invisible"  id="p3">
      <div class="laptop">
        <video loop autoplay muted class="laptop-screen" id="vid">

            <source src="../assets/elmspeakers.mp4"
                    type="video/mp4">

            Sorry, your browser doesn't support embedded videos.
        </video>
        <img class="laptop-right" src="../assets/mac-laptop.png" alt="laptop screenshot">
      </div>
      <img class="phone-right" src="../assets/elm-phone.jpg" alt="phone screenshot">
      <div class="tech-stack" id="tech-elm">
      <img class="tech react" src="../assets/react.png" alt="react logo">
      <img class="tech bs" src="../assets/bootstrap.png" alt="bootstrap logo">
      <img class="tech js" src="../assets/js.png" alt="javascript logo">
      <img class="tech net" src="../assets/netlify.png" alt="netlify logo">
      </div>
    </div>
    <div class="links">
    <a class="project-link" v-bind:href="currentLink" target="_blank">Site</a>
    <a class="project-link" v-bind:href="'https://github.com/mattericbrown/' + currentProject" target="_blank"><img class="github" src="../assets/github.png" alt="github logo"></a>
    </div>
    <div class="carosel">
      <div class="arrow-left" @click='moveLeft' v-if="!one"><div class='arrow-mask-left'></div></div>
      <div class="button-active grow" id="project-one"></div>
      <div class="button-inactive" id="project-two"></div>
      <div class="button-inactive" id="project-three"></div>
      <div class="arrow-right" @click='moveRight' v-if="!three"><div class='arrow-mask-right'></div></div>
    </div>
  </div>
  <div class="hero-img">
   <img class="large-image" src="../assets/mural.jpg" alt="image of a mural in sacramento"/>
  </div>
  <div class="overlay-project">

  </div>

</div>
</template>

<script>

export default {
  name: 'Projects',
  data() {
            return {
                currentProject: 'developer-quiz',
                currentLink: 'http://www.developersquiz.com/',
                one: true,
                two: false,
                three: false
            }
        },
  methods: {
    moveRight:function(){
      let projectOne = document.getElementById('project-one')
      let projectTwo = document.getElementById('project-two')
      let projectThree = document.getElementById('project-three')
      let p1 = document.getElementById('p1');
      let p2 = document.getElementById('p2');
      let p3 = document.getElementById('p3');
      let tech1 = document.getElementById('tech-dq');
      let tech2 = document.getElementById('tech-ml');
      let tech3 = document.getElementById('tech-elm');
      let vid = document.getElementById('vid');

      if(this.one) {
        this.one = false;
        this.two = true;
        p2.classList.remove('invisible');
        p2.classList.add('fade-in');
        p1.classList.add('fade-out');
        tech1.classList.add('fade-out');
        tech1.classList.add('invisible');
        tech2.classList.remove('invisible');
        this.currentLink = 'https://music-lovers-app.herokuapp.com/'
        this.currentProject = 'music_lovers'
        projectOne.classList.remove('button-active');
        projectOne.classList.add('shrink');
        projectOne.classList.add('button-inactive');
        projectTwo.classList.remove('button-inactive');
        projectTwo.classList.remove('shrink');
        projectTwo.classList.add('button-active');
        projectTwo.classList.add('grow');
        vid.play();
      }
      else if(this.two) {
        this.two = false;
        this.three = true;
        p3.classList.remove('invisible');
        p3.classList.add('fade-in');
        p2.classList.add('fade-out');
        p1.classList.add('invisible');
        tech2.classList.add('fade-out');
        tech2.classList.add('invisible');
        tech3.classList.remove('invisible');
        tech3.classList.add('fade-in');
        this.currentLink = 'https://elmspeakers.com/'
        projectTwo.classList.remove('button-active');
        projectTwo.classList.add('shrink');
        projectTwo.classList.add('button-inactive');
        projectThree.classList.remove('button-inactive');
        projectThree.classList.remove('shrink');
        projectThree.classList.add('button-active')
        projectThree.classList.add('grow')
      }
    },
    moveLeft: function(){
      let projectUno = document.getElementById('project-one')
      let projectDos = document.getElementById('project-two')
      let projectTres = document.getElementById('project-three')
      let p_1 = document.getElementById('p1');
      let p_2 = document.getElementById('p2');
      let p_3 = document.getElementById('p3');
      let tech_1 = document.getElementById('tech-dq');
      let tech_2 = document.getElementById('tech-ml');
      let tech_3 = document.getElementById('tech-elm');


      if(this.two) {
        this.two = false;
        this.one = true;
        p_1.classList.remove('invisible');
        p_1.classList.add('fade-in');
        p_2.classList.remove('fade-in');
        p_2.classList.add('fade-out');
        p_2.classList.add('invisible');
        tech_1.classList.add('fade-in');
        tech_1.classList.remove('invisible');
        tech_2.classList.add('fade-out');
        tech_2.classList.add('invisible');
        this.currentLink = "http://www.developersquiz.com/"
        projectDos.classList.remove('button-active');
        projectDos.classList.add('shrink');
        projectDos.classList.add('button-inactive');
        projectUno.classList.remove('button-inactive');
        projectUno.classList.remove('shrink');
        projectUno.classList.add('button-active')
        projectUno.classList.add('grow')
      }
      else if(this.three) {
        this.two = true;
        this.three = false;
        p_2.classList.remove('invisible');
        p_2.classList.add('fade-in');
        p_3.classList.remove('fade-in');
        p_3.classList.add('fade-out');
        p_3.classList.add('invisible');
        tech_2.classList.add('fade-in');
        tech_2.classList.remove('invisible');
        tech_3.classList.add('fade-out');
        tech_3.classList.add('invisible');
        this.currentLink = 'https://music-lovers-app.herokuapp.com/'
        projectTres.classList.remove('button-active');
        projectTres.classList.add('shrink');
        projectTres.classList.remove('grow');
        projectTres.classList.add('button-inactive');
        projectDos.classList.remove('button-inactive');
        projectDos.classList.remove('shrink');
        projectDos.classList.add('button-active');
        projectDos.classList.add('grow');
      }
    }
  }

}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">

h3 {
  text-transform: uppercase;
  font-weight: 500;
  font-size: 2rem;
}

.button-active {
  width:12px;
  height: 12px;
  border-radius: 50%;
  background-color: #443e3c;
  box-shadow: none;
  display: inline-block;
  margin-right: 16px;
  position: relative;
  top: 0px;
}

.button-inactive {
  border-radius: 50%;
  background-color: #443e3c;
  display: inline-block;
  margin-right: 16px;
  width: 12px;
  height: 12px;
}

.carosel {
  position: absolute;
  left: 272px;
  top: 28vw;
}

.arrow-right {
  width: 12px;
  height: 12px;
  background-color: #443e3c;
  position: absolute;
  top: 48%;
  left: 88px;
  transform: translate(-50%, -50%) rotate(45deg);
  &:hover {
    cursor: pointer;
  }
}

.arrow-left {
  width: 12px;
  height: 12px;
  background-color: #443e3c;
  position: absolute;
  top: 48%;
  left: -18px;
  transform: translate(-50%, -50%) rotate(45deg);
  &:hover {
    cursor: pointer;
  }
}

.arrow-mask-right {
  width: 100%;
  height: 100%;
  background-color: #fff;
  position: absolute;
  left: -15%;
  top: 15%;
  right: 0;
  bottom: 0%;
}

.arrow-mask-left {
  width: 100%;
  height: 100%;
  background-color: #fff;
  position: absolute;
  left: 15%;
  top: -15%;
  right: 0%;
  bottom: 0%;
}

.invisible {
  opacity: 0;
}

.fade-out {
  animation: fadeOut 0.9s ease;
}

@keyframes fadeOut {
  0% {
    opacity: 1;
  }

  100% {
    opacity: 0;
  }
}

.fade-in {
  animation: fadeIn 0.9s ease;
}

@keyframes fadeIn {
  0% {
    opacity: 0;
  }

  100% {
    opacity: 1;
  }
}


.grow {
  animation: grow .2s cubic-bezier(.73,.01,.96,.24) forwards;
}

.move-left {
  animation: moveLeft 0.9s ease;
}

@keyframes moveLeft {
  0% {
    transform: translateX(0);
    opacity: 1;
  }

  100% {
    transform: translateX(50px);
  }
}

@keyframes grow {
  0% {
    transform: scale(0.9);
  }

  100% {
    transform: scale(1.5);
  }
}

.shrink {
    animation: shrink .2s cubic-bezier(.73,.01,.96,.24) forwards;
}

@keyframes shrink {
  0% {
    transform: scale(1.5);
  }

  100% {
    transform: scale(0.9);
  }
}

.hidden {
  display: none;
}

.visible {
  display: block;
}

.here {
  color: #FFFFFF;
  font-weight: 500;
  font-size: 2rem;
  position: relative;
}
.projects-wrapper {
  position: absolute;
  top: 66vw;
  left: 33.7vw;
}

.laptop {
  position: relative;
}

.laptop-right {
  position: absolute;
  width: 30vw;
}

.laptop-screen {
  position: absolute;
  width: 21.9vw;
  top: 3vh;
  left: 4vw;
}

.phone-right {
  position: absolute;
  top: 112px;
  left: 30vw;
  width: 7.81vw;
}

.project-link {
  position: relative;
  display: inline;
  margin-right: 16px;
  color: #443e3c;
}

.github-link {
  position: relative;
  display: inline;
}

.github {
  position: relative;
  top: 4px;
  width: 18px;
  height: auto;
}

.links {
  position: absolute;
  left: 0.7vw;
  top: 28vw;
}

.large-image {
  animation: fadeinslow 3.75s cubic-bezier(.73,.01,.96,.24) 0.3s forwards;
  opacity: 0;
  width: 60%;
  height: auto;
  max-width: 1000px;
  position:absolute;
  left: 40%;
  top: 100.5vw;
  margin-right: -7px;
  margin-top: -8px;
}

.overlay-project {
  width: 40vw;
  height: 32vw;
  position: absolute;
  top: 100vw;
  background-color: #fff;
  z-index: 50;
  left: 0;
}

.tech {
  position: relative;
}

.tech-stack {
  position: absolute;
  left: 31vw;
  top: 180px;
}

.gql {
   height: 40px;
    width: auto;
    left: 12vw;
    top: -16px;
}

.ts {
  height: 40px;
  width: auto;
  left: 14vw;
  top: -16px;
}

.styled {
  height: 40px;
  width: auto;
  left: 16vw;
  top: -16px;
}

.rails {
  height: 48px;
  width: auto;
  left: 10vw;
  top: -16px;
}

.ruby {
  height: 40px;
  width: auto;
  left: 12vw;
  top: -16px;
}

.sql {
  height: 52px;
  width: auto;
  left: 14vw;
  top: -16px;
}

.material {
  height: 56px;
  width: auto;
  left: 16vw;
  top: -8px;
}

.react {
  height: 48px;
  width: auto;
  left: 10vw;
  top: -24px;
}

.bs {
   height: 40px;
    width: auto;
    left: 12vw;
    top: -16px;
} 

.js {
  height: 48px;
  width: auto;
  left: 14vw;
  top: -16px;
}

.net {
  height: 40px;
  width: auto;
  left: 16vw;
  top: -16px;
}

@keyframes fadeinslow {
  0% {
    opacity: 0;
  }

  60% {
    opacity: 0;
  }

  100% {
    opacity: 100;
  }
}

@media only screen and (max-width : 413px) {
  .projects-wrapper {
    position: absolute;
    top: 74vh;
    left: 10vw;
  }

  .here {
    color: #443e3c;
    font-weight: 500;
    font-size: 1.2rem;
    position: relative;
  }

  .few {
    font-size: 1.2rem;
  }

  .laptop-right {
    position: relative;
    width: 50vw;
  }

  .laptop-screen {
    position: absolute;
    width: 36.9vw;
    top: 1vh;
    left: 7vw;
  }

  .phone-right {
    position: absolute;
    top: 75px;
    left: 50vw;
    width: 12vw;
  }

  .tech-stack {
    position: absolute;
    left: 35%;
    top: 60vw
  }

  .project-link {
    position: relative;
    display: inline;
    margin-right: 16px;
    top: 64px;
    color: #443e3c;
  }

  .github-link {
    position: relative;
    display: inline;
  }

  .github {
    position: relative;
    top: 4px;
    width: 18px;
    height: auto;
  }

  .carosel {
    position: absolute;
    left: 25%;
    top: 55vw;
    width: 90px;
  }

  #project-one {
    margin-right: 8px;
  }

   #project-two {
    margin-right: 8px;
  }

   #project-three {
    margin-right: 8px;
  }

  .arrow-right {
  width: 12px;
  height: 12px;
  background-color: #443e3c;
  position: absolute;
  top: 48%;
  left: 62px;
  transform: translate(-50%, -50%) rotate(45deg);
  &:hover {
    cursor: pointer;
  }
}

.arrow-left {
  width: 12px;
  height: 12px;
  background-color: #443e3c;
  position: absolute;
  top: 48%;
  left: -12px;
  transform: translate(-50%, -50%) rotate(45deg);
  &:hover {
    cursor: pointer;
  }
}

.arrow-mask-right {
  width: 100%;
  height: 100%;
  background-color: #fff;
  position: absolute;
  left: -15%;
  top: 15%;
  right: 0;
  bottom: 0%;
}

.arrow-mask-left {
  width: 100%;
  height: 100%;
  background-color: #fff;
  position: absolute;
  left: 15%;
  top: -15%;
  right: 0%;
  bottom: 0%;
}

  .gql {
     height: 20px;
    width: auto;
    left: 16vw;
    top: -36px;
  }

  .ts {
    height: 20px;
  width: auto;
  left: 12vw;
  top: -16px;
  }

  .styled {
    height: 20px;
    width: auto;
    left: 0;
    top: -16px;
  }
  .rails {
  height: 20px;
  width: auto;
  left: 16vw;
  top: -40px;
}

.ruby {
  height: 18px;
  width: auto;
  left: 12vw;
  top: -16px;
}

.sql {
  height: 28px;
  width: auto;
  left: 14vw;
  top: -8px;
}

.material {
  height: 28px;
  width: auto;
  left: 7vw;
  top: -36px;
}

.react {
  height: 24px;
  width: auto;
  left: 16vw;
  top: -40px;
}

.bs {
   height: 20px;
    width: auto;
    left: 12vw;
    top: -16px;
} 

.js {
  height: 24px;
  width: auto;
  left: 14vw;
  top: -16px;
}

.net {
  height: 20px;
  width: auto;
  left: 4vw;
  top: -40px;
}
.large-image {
  top: 102vw;
  margin-right: -7px;
  margin-top: -8px;
  }
}
</style>