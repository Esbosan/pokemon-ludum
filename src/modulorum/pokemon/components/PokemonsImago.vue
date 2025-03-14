<template>
  <section>
    <img
    v-if="!revelarepokemon"
    :src="pokemonImago"
    alt=""
    class="brightness-0 h-[200px]" />

    <img
    v-else="revelarepokemon"
    :src="pokemonImago"
    alt=""
    class="h-[200px]" />

  </section>
</template>

<script setup lang="ts">
import { computed } from 'vue';
interface Props {
  pokemonId: number;
  revelarepokemon?: boolean;
}

const props = withDefaults(defineProps<Props>(), {
  revelarepokemon: false,
});

const pokemonImago = computed(
  () =>
    `https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/other/dream-world/${props.pokemonId}.svg`,
);
</script>

<style scoped>
img {
  user-select: none;
  -webkit-user-drag: none;
  -webkit-user-select: none;
  -moz-user-select: none;
  -ms-user-select: none;
}
</style>
