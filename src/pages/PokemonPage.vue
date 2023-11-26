<template>
    <h1 v-if="!pokemon">Please wait...</h1>

    <div v-else>
        <h1>Who's that Pokémon?</h1>
        
        <PokemonPicture 
            :pokemon-id="pokemon.id" 
            :show-pokemon="showPokemon" 
        />

        <PokemonOptions 
            :pokemons="pokemonArr"
            @selection-pokemon="checkAnswer"
        />

        <template v-if="showAnswer">
            <h2 class="fade-in">{{ message }}</h2>
            <button @click="newGame">
                New Game
            </button>
        </template>

    </div>
    
</template>

<script src="./PokemonPage.ts"/>

