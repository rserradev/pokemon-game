<template>
    <section v-if="isLoading" class="flex flex-col justify-center items-center w-screen h-screen">
        <h1 class="text-3xl">Espere por favor</h1>
        <h3 class="animate-pulse">Cargando Pokémons</h3>
    </section>

    <section v-else="isLoading" class="flex flex-col justify-center items-center w-screen h-screen">
        <h1 class="m-5">¿Quién es este Pokémon?</h1>
        <!-- Pokemon Picture -->
        <PokemonPicture />

        <!-- Pokemon Options -->
        <PokemonOptions />
    </section>
</template>

<script lang="ts" setup>
import PokemonOptions from '../components/PokemonOptions.vue';
import PokemonPicture from '../components/PokemonPicture.vue';
import { usePokemonGame } from '../composables/usePokemonGame';

const { gameStatus, isLoading } = usePokemonGame();
</script>