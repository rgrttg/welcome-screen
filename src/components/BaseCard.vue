<script setup>
// import Cardcard from './Cardcard.vue'

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

<!-- <template>
    <Cardcard>
      <template #date>{{ time }}</template>
      <template #heading>Basisbeschäftigung Besuch</template>
      <template #details>Interessierte für den zweiten Kurs werden uns besuchen.</template>
    </Cardcard>
</template> -->

<template>
  <div class="card">

    <h3>
      {{ date }}, &nbsp;{{ time }}
    </h3>

    <h2>
      {{ heading }}
    </h2>

    <h4>
      {{ details }}
    </h4>
  </div>
</template>

<style scoped>
.card {
  color: #ffbfab;
  background-color: #0f05a0;
  border: 1px solid white;
}

h3 {
  color: #eb5e00;
}

h2 {

}

/* .card {
  margin-top: 2rem;
  display: flex;
  position: relative;
  
}

h3 {
  color: #eb5e00;
}

h2 {
  font-size: 1.2rem;
  font-weight: 500;
  margin-bottom: 0.4rem;
}  

.details {
  flex: 1;
  margin-left: 1rem;
  color: #ffbfab;
}  

@media (min-width: 1024px) {
  .card {
    margin-top: 0;
    padding: 0.4rem 0 1rem calc(var(--section-gap) / 2);
    color: #ffbfab;
    border: 1px solid white;
    background-color: #0f05a0;
  }

  .card:before {
    content: ' ';
    border-left: 1px solid var(--color-border);
    position: absolute;
    left: 0;
    bottom: calc(50% + 25px);
    height: calc(50% - 25px);
  }

  .card:after {
    content: ' ';
    border-left: 1px solid var(--color-border);
    position: absolute;
    left: 0;
    top: calc(50% + 25px);
    height: calc(50% - 25px);
  }

  .card:first-of-type:before {
    display: none;
  }

  .card:last-of-type:after {
    display: none;
  }
} */
</style>