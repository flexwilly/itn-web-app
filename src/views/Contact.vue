<template>
  <v-container class="mt-4 mb-4">
    <v-snackbar
      v-model="snackbar"
      :timeout="4000"
      location="top"
      color="purple-lighten-2"
    >
      <span>Message sent successfully.😄</span>
      <v-btn flat color="white" @click="snackbar=false">Close</v-btn>
    </v-snackbar>
    <v-row class="mb-4">
      <v-col class="text-center">
        <h1 class="text-bold text-purple">Contact Us</h1>
        <v-divider color="purple"></v-divider>
        <p class="text-justify ma-2">
          Need a quotation for your next project? Need any assistance in
          determining your website needs? If so we would love to hear from you.
          To get started kindly fill out this form or email us at
          <b>itnomads.ke@gmail.com</b>
        </p>
      </v-col>
    </v-row>
    <v-row class="mb-4">
      <v-col>
        <v-card>
          <v-card-text>
            <v-form ref="form">
              <!---Full Name--->
              <v-text-field
                prepend-icon="mdi-account-circle"
                label="Full Name"
                v-model="details.user_name"
                :rules="nameRules"
                required
              ></v-text-field>
              <!----Email---->
              <v-text-field
                prepend-icon="mdi-email"
                label="Email"
                type="email"
                :rules="emailRules"
                v-model="details.user_email"
                required
              ></v-text-field>
              <!----Message--->
              <v-textarea
                prepend-icon="mdi-table-edit"
                label="Message"
                :rules="messageRules"
                v-model="details.user_message"
                required
              ></v-textarea>
              <v-spacer></v-spacer>
              <v-btn
                class="bg-purple text-white"
                block
                @click="submitForm"
                :loading="loading"
                >Submit</v-btn
              >
            </v-form>
          </v-card-text>
        </v-card>
      </v-col>
    </v-row>
  </v-container>
</template>
<script>
import emailjs from '@emailjs/browser';

export default{
        name:'Contact',
        data(){
                return{
                             details:
                              { user_name:'',
                                user_email:'',
                                user_message:'',
                              }
                              ,
                              nameRules:[
                                v=>!!v || 'Name is required',
                                v=>(v&& v.length >=3) ||'Name must be greater than 3 characters'
                              ],
                              emailRules:[
                              v=>!!v || 'Email is required',
                              ],

                              messageRules:[
                              v=>!!v || 'Message is required',
                              v=>(v&& v.length >=3) ||'Message  must be greater than 3 characters',
                              ],
                              loading:false,
                              snackbar:false,


                }
        },
        methods:{
                async submitForm(){
                    const {valid}= await this.$refs.form.validate();
                    if(valid) {
                      //console.log('Form is valid');
                      this.loading=true;
                      this.sendEmail();
                      this.loading=false;

                      //show snackbar
                      this.snackbar=true;
                       //rest form after submission
                       this.reset();

                  }
                },
                //reset form after submitting
                reset () {
                  this.$refs.form.reset()
                },



                sendEmail(){
                 //create the object holding the mail
                  const custom_mail = { to_name: this.details.user_email,
                    from_name:this.details.user_name,
                    message:this.details.user_message};

                    //send the email using emailjs
                  emailjs.send('service_357n79c','template_wwtq3dm',custom_mail,'-g4zu1BezPd2fLiR0').then(function(response){
                      console.log('SUCCESS!',response.status, response.text);
                  }, function(error){
                     console.log('FAILED...',error);
                  });
                 }

                }
             }
</script>
