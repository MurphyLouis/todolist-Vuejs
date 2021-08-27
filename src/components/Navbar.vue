<template>
    <nav>
        <v-app-bar flat app >
            <v-app-bar-nav-icon class="grey--text" @click="drawer= !drawer"></v-app-bar-nav-icon>
            <v-toolbar-title class="text-uppercase grey--text">
                <span class="font-weight-light">Todo</span>
                <span class="font-weight-bold">LIST</span>
            </v-toolbar-title>
            <v-spacer></v-spacer>
    <v-menu>
        <template v-slot:avtivator="{on, attrs}">
            <v-btn  v-bind="attrs" v-on=on>
                <v-icon left >expand_more</v-icon>
                <span>Menu</span>
            </v-btn>
        </template>
        <v-list>
            <v-list-item v-for="link in links" :key="link.text" router :to="link.route">
                <v-list-item-title>{{link.text}}</v-list-item-title>
            </v-list-item>
        </v-list>
    </v-menu>

            <v-btn text color="grey">
                <span>Sing Out</span>
                <v-icon>exit_to_app</v-icon>
            </v-btn>
        </v-app-bar>
        
        <v-navigation-drawer app v-model="drawer"  class="blue darken-4">
            <v-layout column align-center >
                <v-flex class="mt-5">
                    <v-avatar size="100">
                        <img src="/avatar.png">
                    </v-avatar>
                    <p class="white--text subheading mt-1 text-center">
                      Murphy
                    </p>
                </v-flex>
            </v-layout>
            <v-list dense nav >
                <v-list-item v-for="link in links" :key="link.text" router :to="link.route" >
                    <v-list-item-icon>
                            <v-icon  class="white--text">{{link.icon}}</v-icon>
                    </v-list-item-icon>
                    <v-list-item-content>
                        <v-list-item-title  class="white--text">{{link.text}}</v-list-item-title>
                    </v-list-item-content>
                </v-list-item>
            </v-list>
        </v-navigation-drawer>
    </nav>
</template>

<script>
export default {
    data (){
        return{
            drawer: false,
            links:[
                {icon:'dashboard', text:'Dashboard', route:'/'},
                {icon:'folder', text:'My Projects', route:'/projects'},
                {icon:'person', text:'Team', route:'/team'}
            ]
        }
    }
}
</script>