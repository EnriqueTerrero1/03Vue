<template>

<div v-if="pokemon">
   <h1>
          Pokemon Page <span>#{{ id }}</span>
        </h1>
        <img :src="pokemon.sprites.front_default" :alt="pokemon.name">
</div>
       
</template>

<script>
export default {
  props: {
    id: {
      type: Number,
      required: true,
    },
  },

  methods: {
    async getPokemon() {
      try {
        const Pokemon = await fetch(
          `https://pokeapi.co/api/v2/pokemon/${this.id}`
        ).then((r) => r.json());
        this.pokemon = Pokemon;
        console.log(this.pokemon);
      } catch (error) {
        this.$router.push("/");
        console.log("Redireccionado");
      }
    },
  },
  data() {
    return {
      pokemon: null,
    };
  },
  created() {
    this.getPokemon();
  },
  watch:{
    id(){
    this.getPokemon();
    }
  }
};
</script>

<style>
</style>