<template>
  <div>
    <div>Hello {{ name }} {{ exclamation }}</div>
    <button @click="decrement">+</button>
    <button @click="increment">-</button>
  </div>
</template>

<script lang="ts">
import Vue from "vue";
export default Vue.extend({
  props: ["name"],

  data() {
    return {
      amount: 1
    };
  },

  methods: {
    decrement() {
      this.amount++;
    },

    increment() {
      if (this.amount > 1) {
        this.amount--;
      }
    }
  },

  computed: {
    exclamation(): string {
      return Array(this.amount + 1).join("!");
    }
  }
});
</script>

