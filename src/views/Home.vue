<template>
  <div>
    <v-col>
      <v-carousel
        cycle
        height="500"
        hide-delimiter-background
        show-arrows="hover"
        class="mb-4"
      >
        <v-carousel-item
          v-for="(item,i) in carousel"
          :key="i"
          :src="item.src"
          cover
        >
          <div class="d-none d-sm-flex fill-height justify-center align-center">
            <div
              class="text-heading-4 text-purple font-weight-bold text-capitalize"
            >
              <h1>Software solutions for the modern world</h1>
            </div>
          </div>
        </v-carousel-item>
      </v-carousel>
    </v-col>

    <!--first-section-->
    <v-container>
      <v-row no-gutters class="mb-4">
        <v-col
          xs="12"
          sm="4"
          md="4"
          lg="4"
          class="text-center"
          v-for="icon in icons"
          :key="icon.text"
        >
          <v-avatar size="100">
            <v-img :src="icon.src"></v-img>
          </v-avatar>
          <p class="text-caption text-purple">{{ icon.text }}</p>
        </v-col>
      </v-row>
      <v-divider color="purple"></v-divider>
      <v-row no gutters class="mb-4">
        <v-col class="text-center">
          <h2 class="text-purple mb-4">Join us today.</h2>
          <p class="text-justify">
            At ITN we believe that you deserve to receive high-quality services
            that meet your immediate and long-term needs. We have a dedicated
            team that can develop high-perfomance websites that are scalable and
            have ligh levels of S.E.O. We invite you to be part of our growing
            customer base and enjoy the services we offer.
          </p>
        </v-col>
      </v-row>
      <v-divider color="purple"></v-divider>

      <!---Testimonials-->
      <v-row class="mb-4">
        <v-col>
          <h2 class="text-center text-purple mb-4">What our clients say..</h2>
          <v-slide-group height="100" show-arrows hide-delimiters>
            <v-slide-group-item v-for="t in testimonials" :key="t.name">
              <v-card class="ma-1" color="grey" height="100" width="320">
                <v-card-title class="text-subtitle-2 text-yellow-lighten-4">
                  <v-avatar size="30" class="border">
                    <v-img :src="t.image" cover></v-img>
                  </v-avatar>
                  {{ t.name }}</v-card-title
                >
                <v-card-text class="text-caption">{{ t.text }}</v-card-text>
              </v-card>
            </v-slide-group-item>
          </v-slide-group>
        </v-col>
      </v-row>
    </v-container>
  </div>
</template>
<script>
export default{
        name:'Home',
        data(){
                return{
                    carousel:[

                        {src:'/images/carousel/img-1.jpg'},

                        {src:'/images/carousel/img-2.jpg'},
                        {src:'/images/carousel/img-3.jpg'},
                    ],
                    icons:[
                        {src:'/images/web-dev-icon.png',text:'Custom Website Development'},
                        {src:'/images/graphics-design-icon.png',text:'Graphics Design'},
                        {src:'/images/it-support.png',text:'IT Support Services'}
                    ],
                    testimonials:[
                        {name:'Chris Hudson Omaya',image:'/images/person1.jpg',text:'It was a wonderful experience having had my website made by ITN.'},
                        {name:'Jonas Nzengeli Jokassi',image:'/images/person2.jpg',text:'ITN make wonderful world-class systems.'},
                        {name:'Alvan Mapunda Kombole',image:'/images/person3.jpg',text:'My CMS website is working perfectly thanks to ITN.'},
                        {name:'Brenda Almeida Goncalves', image:'/images/person4.jpg',text:'I enjoyed contracting ITN to build my ecommerce website.'},
                        {name:'Laura Lokech Mboma',image:'/images/person5.jpg',text:'I encourage anyone who wants a world-class website to get in touch with ITN.'}

                    ],


                }
        }
}
</script>
