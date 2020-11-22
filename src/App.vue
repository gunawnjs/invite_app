<template>
  <v-app id="App">
    <Navbar v-if="Navbar"/>
    <v-main class="grey lighten-3">
      <router-view/>
    </v-main>

  </v-app>
</template>

<script>
import Navbar from './components/Navbar';

export default {
  name: 'App',
  components: { Navbar },
  data: () => ({
     Navbar:true,
     links: [
        'Dashboard',
        'Messages',
        'Profile',
        'Updates',
      ],
  }),
  // halaman dimuat ?
  mounted(){
      this.Navbar=this.$route.name == 'Login' ? false:true
  }
};
</script>

<style>
#App{
  font-family:'Montserrat', sans-serif;
}
.wrapper{
  height:auto;
  min-height:100%;
  display:flex;
  flex-direction: column;
}
</style>