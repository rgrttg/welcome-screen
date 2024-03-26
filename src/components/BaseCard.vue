<script setup>
defineProps({
  time: {
    type: String
  },
  date: {
    type: String
  },
  heading: {
    type: String
  },
  details: {
    type: String
  }
})  
</script>

<template>
  <div class="card">

    <h3>
      {{ date }}, &nbsp;{{ time }}&nbsp;Uhr
    </h3>

    <h4>
      {{ heading }}
    </h4>

    <h5>
      {{ details }}
    </h5>
  </div>
</template>

<style scoped>
.card {
  color: var(--color-card-text);
  background-color: var(--color-background-item);
  border: 1px solid var(--color-border);
  margin: 2rem;
  font-size: 28px;
  font-weight: 900;
  line-height: 36px;
  padding: 2rem;
}
h3 {
  color: var(--color-card-date);
}
h5 {
  font-weight: 500;
}
</style>