   <template>
   <v-card
    class="mx-auto my-12"
    max-width="600"
    max-height="600"
    outlined
  >
    <v-img
      height="150"
      src="https://image.tmdb.org/t/p/original/bOGkgRGdhrBYJSLpXaxhXVstddV.jpg"
    ></v-img>

    <v-card-title >{{movie.title}}</v-card-title>

    <v-card-text>
     
      
      <div>{{movie.opening_crawl}}</div>
    </v-card-text>

    <v-divider class="mx-4"></v-divider>

    <v-card-subtitle>Director: {{movie.director}}</v-card-subtitle>
    <v-card-subtitle>Producer: {{movie.producer}}</v-card-subtitle>
    <v-card-text> Release Date {{movie.release_date}}</v-card-text>
    <v-card-actions>
      <v-btn
        color="green"
        block
       @click="openForm"
      >
      CHARACTERS
      </v-btn>
    </v-card-actions>
  </v-card>
</template>


<script>
export default {
   name: 'movie',
   props:['movie'],
    data:() =>({
     }),
     methods:{
       openForm(){
         let id=0;
           id=this.movie.url.substring(28, 29)
           this.$router.push({name: 'Movie.view', params: {id:id}})
       }
     }  
  }
</script>

<style scoped>

</style>