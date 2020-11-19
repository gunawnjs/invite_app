<template>
  <v-app id="inspire">
    <Navbar />
    <v-content class="grey lighten-3">
      <router-view/>
    </v-content>

  </v-app>
</template>

<script>
import Navbar from './components/Navbar';

export default {
  name: 'App',
  components: { Navbar },
  data: () => ({
     links: [
        'Dashboard',
        'Messages',
        'Profile',
        'Updates',
      ],
  }),
};
</script>

<style>
.wrapper{
  height:auto;
  min-height:100%;
  display:flex;
  flex-direction: column;
}
</style>