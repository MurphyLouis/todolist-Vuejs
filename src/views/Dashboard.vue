<template>
  <div class="dashboard">
    <h1 class="subtitle-1 grey--text">Dashboard</h1>
    <v-container grid-list-md class="my-5">

      <v-layout row class="mb-3 ml-4">
        <v-tooltip top>
          <template v-slot:activator="{on,attrs}">
            <v-btn small text color="grey" @click="sortBy('title')" v-bind="attrs" v-on="on">
          <v-icon left small>folder</v-icon>
          <span class="caption text-lowercase">By project name</span>
          </v-btn>
          </template>
          <span>Sort projects by project name</span>
        </v-tooltip>

        <v-tooltip top>
          <template v-slot:activator="{on,attrs}">
            <v-btn  class="ml-4" small text color="grey" @click="sortBy('person')" v-bind="attrs" v-on="on">
          <v-icon left small>person</v-icon>
          <span class="caption text-lowercase">By person </span>
        </v-btn>
          </template>
          <span>Sort projects by person</span>
        </v-tooltip>
        
        
      </v-layout>

      <v-card flat class='mb-1' v-for="project in projects" :key="project.title" >
        <v-layout row wrap  :class="`pa-3 project ${project.status}`">
          <v-flex xs12 md6>
            <div class="caption grey--text">Project title</div>
            <div>{{project.title}}</div>
          </v-flex>
          <v-flex xs6 sm4 md2>
            <div class="caption grey--text">Person</div>
            <div>{{project.person}}</div>
          </v-flex>
          <v-flex xs6 sm4 md2>
            <div class="caption grey--text">Due by</div>
            <div>{{project.due}}</div>
          </v-flex>
          <v-flex xs6 sm4 md2>
            <div  class="right" id="chips-container">
              <v-chip  :class="` ${project.status} white--text caption my-2`" >{{project.status}}</v-chip>
            </div>
          </v-flex>
        </v-layout>
        <v-divider></v-divider>
      </v-card>
      
    </v-container>

  </div>
</template>

<script>
  export default {
    data(){
      return {
        projects:[
          {title:'Design a new website', person:'Mijiniech', due:'2022-01-01' , status:'ongoing', content:'Lorem ipsum dolor sit amet consectetur, adipisicing elit. Fugit, vitae? Dolorem illum dignissimos odio inventore, consectetur beatae aspernatur porro, dicta repellendus impedit distinctio deserunt? Molestias dolore itaque magnam. Veniam, perferendis.'},
          {title:'Code up the home page', person:'Murphy', due:'2021-12-01' , status:'complete',content:'Lorem ipsum dolor sit amet consectetur, adipisicing elit. Fugit, vitae? Dolorem illum dignissimos odio inventore, consectetur beatae aspernatur porro, dicta repellendus impedit distinctio deserunt? Molestias dolore itaque magnam. Veniam, perferendis.'},
          {title:'Design video thumbnails', person:'Musokya', due:'2021-12-05' , status:'complete',content:'Lorem ipsum dolor sit amet consectetur, adipisicing elit. Fugit, vitae? Dolorem illum dignissimos odio inventore, consectetur beatae aspernatur porro, dicta repellendus impedit distinctio deserunt? Molestias dolore itaque magnam. Veniam, perferendis.'},
          {title:'Create a community forem', person:'Louis', due:'2021-12-25' , status:'overdue', content:'Lorem ipsum dolor sit amet consectetur, adipisicing elit. Fugit, vitae? Dolorem illum dignissimos odio inventore, consectetur beatae aspernatur porro, dicta repellendus impedit distinctio deserunt? Molestias dolore itaque magnam. Veniam, perferendis.'}
        ]
      }
    },
    methods:{
      sortBy(prop){
        this.projects.sort((a,b)=>a[prop]<b[prop]? -1:1)
      }
    }
  }
</script>

<style>
.project.complete{
  border-left:3px solid #3cd1c2;
}
.project.ongoing{
  border-left:4px solid orange;
}
.project.overdue{
  border-left:4px solid rgb(182, 62, 62);
}
#chips-container .v-chip.complete {
  background: #3cd1c2;
}
#chips-container .v-chip.ongoing {
  background:orange;
}
#chips-container .v-chip.overdue {
  background: rgb(182, 62, 62);
}
.right{
  margin-left: 40px;
}
</style>
