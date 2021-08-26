<template>
  <div class="team">
    <h1 class="subtitle-1 grey--text">Team</h1>
    
    <v-container class="my-5">

      <v-layout row wrap>
        <v-flex xs12 sm6 md4 lg3 v-for="person in team" :key="person.name" >
          <v-card  class="ma-3 text-center " color="grey lighten-4">
            <v-responsive class="pt-4">
              <v-avatar size="100" class="white">
                <img :src="person.avatar">
              </v-avatar>
            </v-responsive>
            <v-card-text>
              <div class="subtitle-1">{{person.name}}</div>
              <div class="grey--text">{{person.role}}</div>
            </v-card-text>
            <v-card-actions>
              <v-btn text color="blue darken-4">
                <v-icon small left>message</v-icon>
                <span >Message</span>
              </v-btn>
            </v-card-actions>
          </v-card>
        </v-flex>
      </v-layout>
        
    </v-container>

  </div>
</template>

<script>
 

  export default {
  data (){
    return {
      team:[
        {name:'Mijinitech', role:'techcompany',avatar:'avatar.png'},
        {name:'Murphy', role:'Graphic designer',avatar:'avatar.png'},
        {name:'Musokya', role:'Web developer',avatar:'avatar.png'},
        {name:'Louis', role:'Sales and social media',avatar:'avatar.png'},
        {name:'MML', role:'software dev',avatar:'avatar.png'}
      ]
    }
  }
  }
</script>
