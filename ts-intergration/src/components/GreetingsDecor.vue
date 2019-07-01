<template>
  <div>
    <div>Hello {{ name }} {{ exclamation }}</div>
    <button @click="decrement">+</button>
    <button @click="increment">-</button>
  </div>
</template>

<script lang="ts">
import { Vue, Component, Prop } from "vue-property-decorator";
@Component
export default class GreetingsDecor extends Vue {
  @Prop() name!: string;

  amount = 1;

  decrement() {
    this.amount++;
  }

  increment() {
    if (this.amount > 1) {
      this.amount--;
    }
  }

  get exclamation(): string {
    return Array(this.amount + 1).join("!");
  }
}
</script>

