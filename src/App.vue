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
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
  background: url('assets/pexels-bg.jpg');
}

</style>
