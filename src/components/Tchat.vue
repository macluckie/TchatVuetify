<template>
    
    <div>
        <v-chip color="red">{{ name }}</v-chip>
    <v-textarea v-model="message" label="message" >
    </v-textarea>
    <v-btn v-on:click="getMessage">valider message</v-btn>
    </div>
</template>

<script>


export default {
    props:['name'],
    name:"Tchat",
    

    data(){
      return{       

          message:" " ,
          test: 'value'   
          }
      
    },
    methods:{

         getMessage: function() {
            
            return this.$emit('eventData', this.message, )
        }

    }
    
}
</script>

<style  scoped>
div{
    width: 500px;
    margin: auto;
}



    
</style>