<template>
  <section v-if="estPortat || temerePokemon.id === null" class="flex flex-col justify-center items-center w-screen h-screen">
    <h1 class="text-3xl">Espere, por favor</h1>
    <h3 class="animate-pulse">Cargando Pokémons</h3>
  </section>

  <section v-else class="flex flex-col justify-center items-center w-screen h-screen">
    <h1 class="m-5">¿Quién es este Pokémon?</h1>
    <h3>{{ temerePokemon.nomen }}</h3>

    <PokemonsImago :pokemon-id="temerePokemon.id"  :revelare_pokemon="LudumStatus !== LudumStatus.Ludit" />
    <PokemonOptiones />
  </section>
</template>

<script setup lang="ts">
import PokemonOptiones from '../components/PokemonOptiones.vue';
import PokemonsImago from '../components/PokemonsImago.vue';
import { usePokemonLudum } from '../composables/usePokemonLudu';

const { LudumStatus, estPortat, temerePokemon } = usePokemonLudum();


</script>

<style scoped></style>
