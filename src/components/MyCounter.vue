<template>
  <section>
    <h3>Counter: {{ counter }}</h3>
    <h3>Square: {{ squareCounter }}</h3>

    <div>
      <button class="btn" @click="counter++">+1</button>
      <button class="btn" @click="counter--">-1</button>
    </div>
  </section>
</template>

<script lang="ts" setup>
import { useCounter } from '@/composables/useCounter';

interface Props {
  value: number;
}

//import { ref, computed } from 'vue';

// const props = defineProps({
//   value: { type: Number, required: true },
// });

const props = defineProps<Props>();

const { counter, squareCounter } = useCounter(10);
// const counter = ref(props.value);
// const squareCounter = computed(() => counter.value * counter.value);
</script>

<!-- <style scoped>
h1 {
  color: purple;
}
h3 {
  color: brown;
}
</style> -->

<style scoped>
.btn {
  @apply p-5 bg-blue-500 rounded mr-2 hover:bg-blue-800;
}
</style>
