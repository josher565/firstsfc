<template>
  <h2>{{ foodName }}</h2>
  <p>{{ foodDesc }}</p>
  <p v-show="isFavorite">I'm a favorite!!!</p>
  <button v-on:click="toggleFavorite">Favorite</button>
</template>

<script>
export default {
  props: ["foodName", "foodDesc", "isFavorite"],
  emits: ['toggle-favorite'],
  methods: {
    toggleFavorite() {
      this.$emit('toggle-favorite', this.foodName);
    }
  },
};
</script>

<style></style>
