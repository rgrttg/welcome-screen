<script setup>
defineProps({
  msg: {
    type: String,
    required: true
  },
  date: {
    type: String,
    required: true
  }
})
</script>

<template>
  <div class="header">
    <h1>{{ msg }} </h1>
    <h2>{{ date }} </h2>
  </div>
</template>

<style scoped>
.header {
  padding: 2rem;
}
h1 {
  font-size: 62px;
  line-height: 75px;
  letter-spacing: 0em;
  text-align: left;
  font-weight: 901;
  color: var(--color-heading-1);
}

h2 {
  font-size: 62px;
  line-height: 75px;
  letter-spacing: 0em;
  text-align: left;
  font-weight: 500;
  color: var(--color-heading-2);
}
</style>
