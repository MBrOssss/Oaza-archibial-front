<template>
    <div v-show="userIsLogged" id="app">
      <Navigation />
      <router-view/>
    </div>
    
    <div v-show="!userIsLogged" id="app">
      <LoginRegister />
    </div>
</template>

<script>
import Navigation from '@/components/Navigation.vue';
import LoginRegister from '@/components/LoginRegister';

export default ({
  name: "App",
  components: {Navigation, LoginRegister},
  data() {
    return{
      userIsLogged: true,
    }
  }
})
</script>


<style lang="scss">
#app {
  // font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
  background: rgb(240,245,244);
  background: linear-gradient(135deg, rgba(240,245,244,1) 0%, rgba(161,193,227,1) 81%, rgba(189,204,221,1) 100%);
}

</style>
