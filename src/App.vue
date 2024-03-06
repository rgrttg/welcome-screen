<script setup>
import { ref } from 'vue'
import BaseHeader from '@/components/BaseHeader.vue'
import BaseCard from '@/components/BaseCard.vue'
import BaseFooter from '@/components/BaseFooter.vue'

const sheet_id = import.meta.env.VITE_GOOGLE_SHEET_ID;
const api_token = import.meta.env.VITE_GOOGLE_API_KEY;

// const zeit = ref('')
// const datum = ref('')
// const titel = ref('')
// const detail = ref('')

// Test-Array
const items = ref([
      ['11:00', '04.03.2024', 'WS Persönliche Präsentation', 'Badenerstrasse 437', 'highlight'],
      ['12:00', '11.03.2024', 'WS Persönliche Präsentation', 'Badenerstrasse 437', 'default'],
      ['13:00', '18.03.2024', 'WS Persönliche Präsentation', 'Badenerstrasse 437', 'default']
])

// const events = ref('')

// write method to get data from the API
async function fetchData() {
  // returning a promise that is fulfilled once the response is available.
  const res = await fetch(`https://sheets.googleapis.com/v4/spreadsheets/${sheet_id}/values:batchGet?ranges=A2%3AE100&valueRenderOption=FORMATTED_VALUE&key=${api_token}`);
  // ...taking JSON as input and parsing it to produce a JavaScript object.
  const data = await res.json();
  // events.value = data
  
  // display data from the API
  console.log(data)
}

fetchData()

// tineInterval = ref
// onMounted
// timeInterval.value
// updateCurrentDate
// fetchData
// 1000 * 60 * 30
// onBeforeUnmount

// const items = ref([{ message: 'Foo' }, { message: 'Bar' }])

</script>

<template>
  <header>
    <!-- <img alt="Vue logo" class="logo" src="./assets/logo.svg" width="125" height="125" /> -->
    <div class="wrapper">
      <BaseHeader msg="Welcome to Opportunity" date="08.08.2021" />
    </div>
  </header>

  <main>
    
    <!-- Hier loopen  v-for (event, index) -->
    <div v-for="(item, index) in items" :key="index">  
      <BaseCard v-bind:time="item[0]" v-bind:date="item[1]" v-bind:heading="item[2]" v-bind:details="item[3]" />
    </div>

    <!-- <BaseCard time="14.00 Uhr" date="04.03.2024" heading="Basisbeschäftigung" details="Interessierte" />
    <BaseCard time="14.00 Uhr" date="04.03.2024" heading="Basisbeschäftigung" details="Interessierte" /> -->
  </main>

  <footer>
    <BaseFooter />
  </footer>
</template>

<style scoped>
header {
  line-height: 1.5;
}

.logo {
  display: block;
  margin: 0 auto 2rem;
}

@media (min-width: 1024px) {
  header {
    display: flex;
    place-items: center;
    padding-right: calc(var(--section-gap) / 2);
  }

  .logo {
    margin: 0 2rem 0 0;
  }

  header .wrapper {
    display: flex;
    place-items: flex-start;
    flex-wrap: wrap;
  }
}
</style>
