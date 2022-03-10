<template>
  <v-card>
  <v-card-title>
      <h3>
          {{this.movie.title}}
      </h3>
      <v-spacer/>
      <v-btn
         color="green"
         text
         outlined
         @click="$router.back()">
          back
      </v-btn>
   </v-card-title>

   <v-img
      height="150"
      src="https://image.tmdb.org/t/p/original/bOGkgRGdhrBYJSLpXaxhXVstddV.jpg"
    ></v-img>

    
    <v-card-text>
      
      <div>{{movie.opening_crawl}}</div>
    </v-card-text>

    <v-divider class="mx-4"></v-divider>

    <v-card-subtitle>Director: {{movie.director}}</v-card-subtitle>
    <v-card-subtitle>Producer: {{movie.producer}}</v-card-subtitle>
    <v-card-text> Release Date {{movie.release_date}}</v-card-text>
    <v-divider/>
    <v-card-title >CHARACTERS</v-card-title>
     <v-divider class="mx-4"></v-divider>
      

    <v-card-text>
      <v-carousel :show-arrows="false"  >
    <v-carousel-item
      v-for="(item,i) in movie.characters"
      :key="i"
      :src="item.src"
    >
     <people :people1="item">
          </people>
    
    </v-carousel-item>
  </v-carousel>
       
    </v-card-text>
  </v-card>

</template>

<script>
import people from '../components/people.vue';
export default {
  components: { people },
    name:"movieform",
    data:() =>({
      id:1,
      movie:{},
      

    }), 
    created(){

    },
  mounted(){
   this.getMovie()
  },
  methods:{
    getMovie(){
         this.loading = true;
         const url ="https://swapi.dev/api/films/"+ this.$route.params.id;
          this.axios.get(url).then(response => {
                this.movie = response.data;
            this.loading = false;

          })
      },
   }
}
</script>
