<template>
  <div>
    <v-toolbar>
      <!--Hamburger icon-->
      <v-app-bar-nav-icon @click="drawer = !drawer"></v-app-bar-nav-icon>
      <v-avatar size="40">
        <v-img src="/images/logo-2-itn.png"></v-img>
      </v-avatar>
      <v-toolbar-title>ITNomads</v-toolbar-title>
      <v-spacer></v-spacer>
      <!---Menu tab-->
      <v-btn prepend-icon="mdi-arrow-down-drop-circle" color="grey">
        Menu
        <v-menu activator="parent" open-on-hover>
          <v-list class="text-purple-lighten-2">
            <v-list-item
              v-for="link in links"
              :key="link.text"
              router
              :to="link.route"
            >
              <v-list-item-title>{{ link.name }} </v-list-item-title>
            </v-list-item>
          </v-list>
        </v-menu>
      </v-btn>
    </v-toolbar>
    <!--side navigation-->
    <v-navigation-drawer class="bg-purple text-white" v-model="drawer">
      <v-container>
        <v-row>
          <v-col class="text-center">
            <v-avatar size="100">
              <v-img src="/images/logo-2-itn.png"></v-img>
            </v-avatar>
          </v-col>
        </v-row>
        <!---Apply space between the rows-->
        <v-spacer></v-spacer>
        <v-row>
          <v-col>
            <v-list v-for="link in links" :key="link.name">
              <v-list-item
                :title="link.name"
                :prepend-icon="link.icon"
                router-link
                :to="link.route"
              ></v-list-item>
              <v-divider></v-divider>
            </v-list>
          </v-col>
        </v-row>
      </v-container>
    </v-navigation-drawer>
  </div>
</template>
<script>
export default{
        name:"NavBar",
        data(){
             return{
                drawer:false,
                links:[
                         {name:'Home',icon:'mdi-home',route:'/'},
                         {name:'About',icon:'mdi-information-outline',route:'/about'},
                         {name:'Services',icon:'mdi-image-filter-vintage',route:'/services'},
                         {name:'Contact',icon:'mdi-phone-in-talk',route:'/contact'}

                ]
             }
        }
}
</script>
