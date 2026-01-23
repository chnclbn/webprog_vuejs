<script setup>
import { ref, onMounted } from 'vue'
import { supabase } from './lib/supabaseClient'

const instruments = ref([])
const errorMsg = ref('') // Store error messages here

async function getInstruments() {
  try {
    
    const { data, error } = await supabase.from('instruments').select()
    
    
    if (error) {
        errorMsg.value = "Supabase Error: " + error.message
        console.error(error)
    } 
    
    else if (!data || data.length === 0) {
        errorMsg.value = "Success, but database is empty! (Add rows in Supabase)"
    } 
   
    else {
        instruments.value = data
    }
  } catch (err) {
      errorMsg.value = "System Error: " + err.message
  }
}

onMounted(() => {
   getInstruments()
})
</script>

<template>
  <div style="padding: 20px; font-family: sans-serif;">
    <h1>Debug Status:</h1>
    
    <div v-if="errorMsg" style="color: red; border: 1px solid red; padding: 10px;">
      {{ errorMsg }}
    </div>

    <ul v-else>
      <li v-for="instrument in instruments" :key="instrument.id">
        {{ instrument.name }}
      </li>
    </ul>
  </div>
</template>