<script setup lang="ts">
import { ref, computed } from 'vue';

defineProps<{ msg: string }>();

const count = ref(0);
const inputs = ref([
  {
    key: 0,
    value: 0,
  },
]);
inputs.value.push({
  key: 1,
  value: '5',
});
const sum = computed(() =>
  inputs.value.map((x) => Number(x.value)).reduce((a, b) => a + b, 0)
);
</script>

<template>
  <div>
    <input
      v-for="inp in inputs"
      :key="inp.key"
      type="text"
      v-model="inp.value"
    />
  </div>
  Result sum : {{ sum }}
</template>

<style scoped>
.read-the-docs {
  color: #888;
}
</style>
