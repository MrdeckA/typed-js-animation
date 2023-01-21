<template>
  <div>
    <header>
      <div class="centered">
        <div class="welcome">Hello ! My name is Mériadeck AMOUSSOU</div>
        <span>I'm a </span><span id="typed" ></span><span id="space"></span>
      </div>
    </header>
  </div>
</template>

<script>
export default {
  name: 'IndexPage',
  data(){
    return{
      sets: 2
    }
  },
  mounted() {
    this.iterating(`Web Developper`.toUpperCase());
    
  },
  methods: {
    iterating(iterating) {
      let i = 0
      let chaine = ''

      setInterval(() => {
        if (i < iterating.length) {
          chaine = chaine + iterating[i]
          document.getElementById('typed').innerHTML = chaine
          i++
        } else {
          if(this.sets===1){
            iterating=(`Web Developper`.toUpperCase())
            this.sets=2
          }
          else if(this.sets===2){
            iterating=(`Mobile Developper`.toUpperCase())
            this.sets=3
          }
          else if(this.sets===3){
            iterating=(`Full Stack Javascript Developper`.toUpperCase())
            this.sets=1
          }
          chaine=''
          i = 0
        }
      }, 400)
    },
  },
}
</script>
<style scoped>
#space {
  padding: 0 0.1em;
  background-color: white;
  animation-name: anim;
  animation-duration: 300ms;
  animation-iteration-count: infinite;
  animation-timing-function: linear;
}

@keyframes anim {
  0% {
    background-color: black;
  }
  100% {
    background-color: white;
  }
}
header {
  background-image: url('../assets/images/bg-gradient.jpg');
  height: 100vh;
  color: white;
  text-align: center;
  background-size: cover;
  
}

.centered {
  position: relative;
  top: 40vh;
  left: 0;
  font-size: 2em;
}

.welcome{
  color: gray
}
</style>
