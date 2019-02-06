<template>
    <div>

   
    <v-timeline>
      <v-timeline-item
        v-for="conversation in conversations"
        :key="conversation"
        color="red lighten-2"
        large
      >
        <span slot="opposite">{{conversation.user}}</span>
        <v-card class="elevation-2">
          <v-card-title class="headline">message</v-card-title>
          <v-card-text>
                    {{conversation.message}}        
      </v-card-text>
        </v-card>
      </v-timeline-item>
    </v-timeline>


    </div>
</template>


<script>


export default 
{
    name:'Timeline',
    props: {
        
        conversations: Array,
        
    },

    data() {
        return {

        }
    },

    methods: {
        
       
    },


    
}
</script>


<style scoped>

</style>
