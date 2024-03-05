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
    <h1 class="green">{{ msg }} </h1>
    <h2>{{  date }} </h2>
  </div>
</template>

<style scoped>
h1 {
  /* font-weight: 500;
  font-size: 2.6rem;
  position: relative;
  top: -10px; */
  /* font-family: Inter; */
  font-size: 62px;
  font-weight: 900;
  line-height: 75px;
  letter-spacing: 0em;
  text-align: left;
  color: #323D4A;
}

h2 {
  /* font-size: 1.2rem; */
  /* font-family: Inter; */
  font-size: 62px;
  font-weight: 500;
  line-height: 75px;
  letter-spacing: 0em;
  text-align: left;
  color: #9AA7B1;
}

.header h1,
.header h2 {
  text-align: center;
}

@media (min-width: 1024px) {
  .header h1,
  .header h2 {
    text-align: left;
  }
}
</style>
