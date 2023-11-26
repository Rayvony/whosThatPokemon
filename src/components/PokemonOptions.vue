<template>
  <div class="options-container">
    <ul>
      <li v-for="pokemon in pokemons" 
          :key="pokemon.id"
          @click="$emit( 'selectionPokemon', pokemon.id )">
          {{ pokemon.name }}
      </li>
    </ul>
  </div>
</template>

<script setup lang="ts">
import { Pokemon } from '../interfaces/pokemon';

defineProps<{
  pokemons: Pokemon[]
}>()

</script>

<style scoped>
ul {
    list-style-type: none;
}
li {
    padding: 10px;
    background-color: white;
    border-radius: 5px;
    border: 1px solid rgba(0, 0, 0, 0.2);
    cursor: pointer;
    margin-bottom: 15px;
    width: 250px;
    color: black;
    text-transform: capitalize;
}

li:hover {
    background-color: rgba(185, 185, 185, 0.918);

}

.options-container {
    display: flex;
    justify-content: center;
}
</style>