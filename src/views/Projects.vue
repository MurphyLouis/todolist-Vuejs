<template>
  <div class="projects">
    <h1 class="subtitle-1 grey--text">Projects</h1>

    <v-container class="my-5">
        <v-expansion-panels>
          <v-expansion-panel v-for="project in myProjects" :key="project.title">
            <v-expansion-panel-header>
              {{project.title}}
            </v-expansion-panel-header>
            <v-expansion-panel-content class="grey--text">
              <div class="font-weight-bold">due by {{project.due}}</div>
              <div>{{ project.content }}</div>
            </v-expansion-panel-content>
          </v-expansion-panel>
        </v-expansion-panels>
    </v-container>

  </div>
</template>

<script>
 

  export default {
    data(){
      return{
         projects:[
          {title:'Design a new website', person:'Mijiniech', due:'1st Jan 2022' , status:'ongoing', content:'Lorem ipsum dolor sit amet consectetur, adipisicing elit. Fugit, vitae? Dolorem illum dignissimos odio inventore, consectetur beatae aspernatur porro, dicta repellendus impedit distinctio deserunt? Molestias dolore itaque magnam. Veniam, perferendis.'},
          {title:'Code up the home page', person:'Murphy', due:'1st Dec 2021' , status:'complete',content:'Lorem ipsum dolor sit amet consectetur, adipisicing elit. Fugit, vitae? Dolorem illum dignissimos odio inventore, consectetur beatae aspernatur porro, dicta repellendus impedit distinctio deserunt? Molestias dolore itaque magnam. Veniam, perferendis.'},
          {title:'Design video thumbnails', person:'Musokya', due:'5th Dec 2021' , status:'complete',content:'Lorem ipsum dolor sit amet consectetur, adipisicing elit. Fugit, vitae? Dolorem illum dignissimos odio inventore, consectetur beatae aspernatur porro, dicta repellendus impedit distinctio deserunt? Molestias dolore itaque magnam. Veniam, perferendis.'},
          {title:'Create a community forem', person:'Louis', due:'20st Dec 2021' , status:'overdue', content:'Lorem ipsum dolor sit amet consectetur, adipisicing elit. Fugit, vitae? Dolorem illum dignissimos odio inventore, consectetur beatae aspernatur porro, dicta repellendus impedit distinctio deserunt? Molestias dolore itaque magnam. Veniam, perferendis.'},
          {title:'Code up the home page...again', person:'Murphy', due:'1st Dec 2021' , status:'complete',content:'Lorem ipsum dolor sit amet consectetur, adipisicing elit. Fugit, vitae? Dolorem illum dignissimos odio inventore, consectetur beatae aspernatur porro, dicta repellendus impedit distinctio deserunt? Molestias dolore itaque magnam. Veniam, perferendis.'}
        ]
      }
    },
    computed:{
      myProjects(){
        return this.projects.filter(project=>{
          return project.person==='Murphy'
        })
      }
    }
  
  }
</script>
