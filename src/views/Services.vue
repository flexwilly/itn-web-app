<template>
  <v-container>
    <h1 class="text-center text-purple">Our Services</h1>
    <v-divider></v-divider>
    <v-row>
      <v-col>
        <p class="text-justify ma-2">
          At ITN we believe that anything is possible. We have an unfettered
          desire to solve your problems. From the small business in need of a
          static website to an enterprise-level company with complex system
          requirements, ITN has a ready team that will complete the task.
        </p>
      </v-col>
    </v-row>
    <v-divider color="purple"></v-divider>
    <v-row class="mt-4 mb-4">
      <v-col
        xs="12"
        sm="12"
        md="6"
        lg="4"
        v-for="s in services"
        :key="s.title"
        class="text-center"
      >
        <v-avatar size="180" class="border">
          <v-img :src="s.icon"></v-img>
        </v-avatar>
        <p class="text-subtitle text-purple">{{ s.title }}</p>
        <p>{{ s.desc }}</p>
      </v-col>
    </v-row>
    <v-divider color="purple"></v-divider>
    <v-row>
      <v-col class="text-center">
        <h2 class="text-purple">Talk To Us...</h2>
        <p class="text-justify">
          Get In touch with us and tell us what you are interested in. We are
          ready to meet your web and design needs. Explore our wide variety of
          services on offer.
        </p>
        <v-btn
          flat
          variant="text"
          size="sm"
          color="purple"
          class="pa-2 mt-4 "
          router-link
          to="/contact"
        >
          Contact Us
        </v-btn>
      </v-col>
    </v-row>
  </v-container>
</template>
<script>
export default{
        name:'Services',
        data(){
                return {
                    services:[
                        {title:'Web Development & Design Services',desc:'Content Management Solutions, E-Commerce, Custom Development',icon:'/images/services/web-dev.png'},
                        {title:'Digital Marketing Services',desc:'Social Media Marketing, Search Engine Marketing',icon:'/images/services/digital-marketing.png'},
                        {title:'IT Support Services',desc:'Desktop and Network Support, Backup and Disaster Recovery, Server and Hardware Sales',icon:'/images/services/it-support.png'},
                        {title:'Mobile Application Development',desc:'Custom Mobile Applications',icon:'/images/services/mobile-dev.png'},
                    ]
                }
        }
}
</script>
