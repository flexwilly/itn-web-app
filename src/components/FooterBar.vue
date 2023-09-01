<template>
  <div>
    <v-footer class="bg-grey-lighten-2">
      <v-container>
        <v-row>
          <v-col sm="4" md="4" lg="4" xl="4" class="text-center">
            <h4 class="ma-2">Location</h4>
            <div class="text-purple-lighten-2">
              <p
                class="ma-2"
                v-for="location in locations"
                :key="location.name"
              >
                <v-icon icon="mdi-city"></v-icon>{{ location.name }}
              </p>
            </div>
          </v-col>
          <v-col sm="4" md="4" lg="4" xl="4" class="text-center">
            <h4 class="ma-2">Quick Links</h4>
            <div v-for="link in links" :key="link.name" class="mb-2">
              <v-btn
                router-link
                :to="link.route"
                variant="text flat"
                color="purple-lighten-2"
                size="small"
              >
                {{ link.name }}
              </v-btn>
            </div>
          </v-col>
          <v-col sm="4" md="4" lg="4" xl="4" class="text-center">
            <h4 class="ma-2">Socials</h4>
            <div v-for="s in socials" :key="s.name">
              <v-btn
                variant="text flat"
                color="purple-lighten-2"
                :prepend-icon="s.icons"
                :href="s.route"
              >
              </v-btn>
            </div>
          </v-col>
        </v-row>
        <v-row>
          <v-col class="text-center mt-3">
            <p class="font-weight-bold">
              © {{ new Date().getFullYear() }} - ITN
            </p>
          </v-col>
        </v-row>
      </v-container>
    </v-footer>
  </div>
</template>
<script>
export default{
    name:'Footer',
    data(){
       return{
        socials:[
        {name:'Twitter', icons:'mdi-twitter',route:'#'},
        {name:'Facebook',icons:'mdi-facebook',route:'#'},
        {name:'LinkedIn',icons:'mdi-linkedin',route:'https://www.linkedin.com/in/it-nomad-8abb65214/'},
        {name:'Instagram',icons:'mdi-instagram',route:'https://www.instagram.com/itnomads.ke/'},
       ],
       links:[
        {name:'Home',route:'/',icon:'mdi-home'},
        {name:'About',route:'/about',icon:'mdi-information-outline'},
        {name:'Services',route:'/services',icon:'mdi-image-filter-vintage'},
        {name:'Contact',route:'/contact',icon:'mdi-phone-in-talk'},
      ],
      locations:[
        {name:'Nairobi,Kenya'},
        {name:'Luanda,Angola'},
        {name:'Ndola,Zambia'},
      ]
      }
    }

}
</script>
