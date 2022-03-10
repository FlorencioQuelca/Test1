<template>
  <div>
    <h1>
      {{ people.name }}
    </h1>
    <br/>
   <v-img
      height="150"
      src="https://image.tmdb.org/t/p/original/bOGkgRGdhrBYJSLpXaxhXVstddV.jpg"
    ></v-img>
<br/>
  
    <v-chip class="ma-2" color="success" outlined>
      Height : {{ people.height }}
    </v-chip>
    <v-chip class="ma-2" color="red" outlined>
      Mass : {{ people.mass }}
    </v-chip>
    <v-chip class="ma-2" color="orange" outlined>
      Hair color : {{ people.hair_color }}
    </v-chip>
    <v-chip class="ma-2" color="blue" outlined>
      Skin color : {{ people.skin_color }}
    </v-chip>
    <v-chip class="ma-2" color="green" outlined>
      Eye color : {{ people.eye_color }}
    </v-chip>
     <v-chip class="ma-2" color="blue" outlined>
      Skin color : {{ people.skin_color }}
    </v-chip>
    <v-chip class="ma-2" color="black" outlined>
      Gender : {{ people.gender }}
    </v-chip>
    <v-chip class="ma-2" color="black" outlined>
      Birth year : {{ people.birth_year }}
    </v-chip>
    <br/>
     url people: {{ people1 }}
  </div>
</template>

<script>
export default {
  name: "people",
  props: ["people1"],
  data: () => ({
    people: {},
  }),
  mounted() {
    this.getPeople();
  },
  methods: {
    getPeople() {
      this.loading = true;
      const url = this.people1;
      this.axios.get(url).then((response) => {
        this.people = response.data;
        this.loading = false;
      });
    },
  },
};
</script>

<style scoped></style>
