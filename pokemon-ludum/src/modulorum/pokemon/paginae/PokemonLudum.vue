<template>
  <section
    v-if="estPortat || temerePokemon.id === null"
    class="flex flex-col justify-center items-center w-screen h-screen"
  >
    <h1 class="text-3xl">Espere, por favor</h1>
    <h3 class="animate-pulse">Cargando Pokémons</h3>
  </section>

  <section v-else class="flex flex-col justify-center items-center w-screen h-screen">
    <h1 class="m-5">¿Quién es este Pokémon?</h1>
    <!-- <h3>{{ temerePokemon.nomen }}</h3> -->
    <h3 class="capitalize my-3">{{ ludumStatus }}</h3>

    <div class="h-20">
      <button
      v-if="LudumStatus === LudumStatus"
      @click="sequentiOptiones(4)"
      class="bg-blue-500 text-white p-2 rounded-xl hover:bg-blue-700 transition-all">
        ¿Jugar de nuevo?
      </button>
    </div>

    <PokemonsImago
      :pokemon-id="temerePokemon.id"
      :revelare_pokemon="ludumStatus !== LudumStatus.Ludit"
    />
    <PokemonOptiones
      :optiones="optiones"
      @electus-optio="examineResponsio"
      :non-eligere="ludumStatus !== LudumStatus.Ludit"
      :rected-responsio="temerePokemon.id"
    />
  </section>
</template>

<script setup lang="ts">
import PokemonOptiones from '../components/PokemonOptiones.vue';
import PokemonsImago from '../components/PokemonsImago.vue';
import { usePokemonLudum } from '../composables/usePokemonLudu';
import { LudumStatus } from '../interfaces';

const {
  ludumStatus,
  estPortat,
  temerePokemon,
  pokemonOptiones: optiones,
  examineResponsio,
  sequentiOptiones,
} = usePokemonLudum();

// const cumElectusOptio = (valorem:number) =>{}
</script>

<style scoped></style>
