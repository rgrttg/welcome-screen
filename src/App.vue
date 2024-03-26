<script setup>
import { ref } from 'vue'
import BaseHeader from '@/components/BaseHeader.vue'
import BaseCard from '@/components/BaseCard.vue'
import BaseFooter from '@/components/BaseFooter.vue'

const sheet_id = import.meta.env.VITE_GOOGLE_SHEET_ID;
const api_token = import.meta.env.VITE_GOOGLE_API_KEY;

// Test-Array
// wird noch gebraucht solange am CSS rumgeschraubt wird (zuviele Google-API Anfragen!)
//
// const items = ref([
//       ['14:00', '04.03.2024', 'Basisbeschäftigung Besuch', 'Interessierte für den zweiten Kurs werden uns besuchen', 'highlight'],
//       ['12:00', '11.03.2024', 'WS Persönliche Präsentation', 'Badenerstrasse 437', 'default'],
//       ['15:00', '27.03.2024', 'Oster Apero', 'Mit DJ, Easter-Eggs suche etc.', 'default']
// ])

const events = ref('')

// write method to get data from the API
async function fetchData() {
  // returning a promise that is fulfilled once the response is available.
  const res = await fetch(`https://sheets.googleapis.com/v4/spreadsheets/${sheet_id}/values:batchGet?ranges=A2%3AE100&valueRenderOption=FORMATTED_VALUE&key=${api_token}`);
  // ...taking JSON as input and parsing it to produce a JavaScript object.
  const data = await res.json();

  // events.value = data
  events.value = data.valueRanges[0].values
  
  // display data from the API
  // console.log(data) // => spreadsheet
  // console.log(events.value) // 1.=> Proxy(Object) 2.=> Proxy(Array)
  
}

fetchData()

// TODO: add function to refresh data
//
// timeInterval = ref
// onMounted
// timeInterval.value
// updateCurrentDate
// fetchData
// 1000 * 60 * 30
// onBeforeUnmount

</script>

<template>
  <div class="screen">
    <div class="child1">
      <header>
        <BaseHeader msg="Welcome to Opportunity" date="08.08.2021" />
      </header>
      
      <main>  
        <!-- Hier loopen  v-for (event, index) -->
        <!-- <div v-for="(item, index) in items" :key="index">   -->
        <div v-for="(item, index) in events" :key="index">  
          <BaseCard v-bind:time="item[0]" v-bind:date="item[1]" v-bind:heading="item[2]" v-bind:details="item[3]" />
        </div>
      </main>
    </div>
    
    <div class="child2">
      <footer>
        <BaseFooter />
      </footer>
    </div>
  </div>
</template>
    
<style scoped>
.screen {
  display: flex;
  flex-direction: column;
  justify-content: space-between;
  height: 1920px  ;
  max-width: 1080px;
  background-color: var(--color-background-soft);
}
</style>
