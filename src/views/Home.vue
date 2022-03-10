<template>
  <v-card
   outlined
   :loading="loading"
  >
    <v-card-title>
    LIST OF MOVIES
    </v-card-title>
    <v-divider/>
     
  <v-card-text>


      <v-row>
        <v-col  cols="12" md="6" sm ="6"   v-for="(row,index) in movies" :key="index" >
        <movie :movie="row"
               ></movie>
        </v-col>
      </v-row>
 
 
  </v-card-text>

  </v-card>
</template>

<script>
import movie from '../components/movie.vue'


export default {
  name: 'Home',
  components: {
    movie
  },
  data: () => ({
     films: {},
    movies:[],
    loading: false,

     
    }),
    mounted(){
      this.getFilms()
    },
    methods:{
      getFilms(){
         this.loading = true;

         const url ="https://swapi.dev/api/films";
          this.axios.get(url).then(response => {
                this.movies = response.data.results;
                 this.loading = false;

          })
      },
    }
  
}
</script>
