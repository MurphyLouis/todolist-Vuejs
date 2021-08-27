<template>
    <v-dialog  max-width="600px">
        <template v-slot:activator="{on,attrs}">
            <v-btn small v-bind="attrs" v-on="on" class="success">
                Add new project
            </v-btn>
        </template>
        <v-card>
            <v-card-title>
                <h2>Add a New Project</h2>
            </v-card-title>
            <v-card-text>
                <v-form class="px-3" ref="form">
                    <v-text-field label="Title" v-model="title" prepend-icon="folder" :rules="inputRules"></v-text-field>
                    <v-textarea :rules="inputRules" label="Information" v-model="content" prepend-icon="edit"></v-textarea>

                    <v-menu max-width="290" >
                        <template  v-slot:activator="{on,attrs}">
                            <v-text-field  :value="due" label="Due date" prepend-icon="date_range" v-bind="attrs" v-on="on" :rules="inputRules"></v-text-field>
                        </template>
                        <v-date-picker  v-model="due"></v-date-picker>
                    </v-menu>

                    <v-btn text class="success mx-0 mt-3" @click="submit">ADD PROJECT</v-btn>
                </v-form>
            </v-card-text>
        </v-card>
    </v-dialog>
</template>
<script>
export default {
    
     data(){
            return{
                title:'',
                content:'',
                due:null,
                inputRules:[
                    v => v.length >=3 || 'Minimun lenght is 3 characters'
                ]
            }
        },
     methods:{
            submit(){
                if(this.$refs.form.validate()){
                    console.log(this.title,this.content)
                }
            }
        },
     computed: {
    
        }
    
}
</script>