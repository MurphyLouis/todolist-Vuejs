<template>
  <v-app id='app' >
    <Navbar />
    <v-content class="ml-4 mb-4 mr-12">
      <router-view></router-view>
    </v-content>
  </v-app>
</template>

<script>
import Navbar from '@/components/Navbar'

export default {
  name: 'App',
  components:{Navbar},
  data(){
    return{

    }
  }
};
</script>
<style>
#app{
  background-color:white;
}
</style>
