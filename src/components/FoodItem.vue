<template>
  <h2>{{ foodName }}</h2>
  <p>{{ foodDesc }}</p>
  <p v-show=foodIsFavorite>I'm a favorite!!!</p>
  <button v-on:click="toggleFavorite">Favorite</button>
</template>

<script>
export default {
  data() {
    return {
      foodIsFavorite: this.isFavorite,
    };
  },
  methods: {
    toggleFavorite() {
      this.foodIsFavorite = !this.foodIsFavorite;
    },
  },
  props: {
    foodName: {
      type: String,
      required: true,
    },
    foodDesc: {
      type: String,
      required: false,
      default: "This is the default description.",
      validator: function (value) {
        let result = true;
        if (value.length < 20 && value.length > 50) result = false;
        return result;
      },
    },
    isFavorite: {
      type: Boolean,
      required: false,
      default: false,
    },
  },
};
</script>

<style></style>
