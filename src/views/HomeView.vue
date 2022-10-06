<template>
  <v-container>
        <v-row>
          <v-col
            v-for="budala in budale"
            :key="budala.ime"
            cols="4"
          >
            <v-card height="200" >
            <h1>{{budala.nadimak}}</h1>
          </v-card>
          </v-col>
        </v-row>
      </v-container>
</template>

<script>

export default {
  name: 'HomeView',
  data(){
    return{
      budale:[]
    }
  },
  created(){
    console.log('created')
    this.getData();
  },

  methods:{
    getData(){
      let api='https://my-json-server.typicode.com/HZHBKANJINA/users-api/idoli'
        this.axios.get(api).then((response) => {
        console.log(response.data)
        this.budale=response.data
      })
    }
  }
}
</script>
