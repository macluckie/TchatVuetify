<template>
  <v-app>
    <v-toolbar app>
      <v-toolbar-title class="headline text-uppercase">
        <span>testappvuetify</span>
   
      </v-toolbar-title>
      <v-spacer></v-spacer>
     
    </v-toolbar>

    <v-content >
     <div v-if="displayUser">

      <v-text-field label="User" 
                    v-model="userName"
                    class="user"
                    
                    ></v-text-field>   
      <v-btn v-on:click="eventparent">event</v-btn>
     </div>


      
     <Tchat v-if="displayarea"
            v-bind:name="userName"
            v-on:eventData="showChildData"
             />
            
    <Timeline v-bind:conversations="theTchat"
              > </Timeline>



             
    </v-content>
  </v-app>
</template>

<script>
import Tchat from './components/Tchat.vue'
import Timeline from './components/Timeline.vue'


export default {
  name: 'App',
  components: {    
    Tchat,
    Timeline
    
  },
  data () {
    return {
      displayarea: false,
      userName: ' ',
      messages:' ',
      displayUser: true,
      theTchat: [{user: this.userName, message: this.messages}]

      

    }
  },
  methods: {
    eventparent: function(){

      if (this.userName.length > 5) {
       
        this.displayUser = false;
        this.displayarea = true;
        return this.displayarea;
      }
      
    },

    showChildData: function(data){

        this.messages  = data;

    }
  }
}
</script>

<style scoped>
  .user
  {
    width: 10%;
  }
</style>
