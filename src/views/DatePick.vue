<template>

    <div class="picker">
      
        <h1>Pick your dates</h1>
        <VueDatePicker v-model="date"  range format="MM/dd/yyyy" value-format="MM-dd-yyyy"/>
        
        <!---VueDatePicker v-model="date" no-seconds-overlay enable-seconds /--->
        <!---From: <VueDatePicker mode="date" v-model="fromdate" /><BR/>
        To:<VueDatePicker mode="date" v-model="todate" />
        P>
          Date: {{  date.toJSON() }}
        </P--->
        <BR/>
        Email:  
        <input type="text" v-model="email"> 
        <BR/><BR/>
        <button type="submit" @click="submit">
             Submit Reservation Request
        </button>
    
    </div>

</template>

<script setup>
import { ref, onMounted } from 'vue';

const date = ref();

// For demo purposes assign range from the current date
onMounted(() => {
const startDate = new Date();
const endDate = new Date(new Date().setDate(startDate.getDate() + 7));
date.value = [startDate, endDate];
})
</script>


<style>

  .picker {
    xxmargin-left: 25%;
    xxmargin-right: 25%;
    display: grid;
    xxbackground: yellow;
    place-items: center;
    xxgrid-template-columns: repeat(auto-fill, minmax(25rem, 1fr));
    grid-gap: .4rem;
    xxmax-width: 88rem;
    margin: 0rem auto;
    padding: 0 36rem;
  }
  div.pickerxx {
    margin: 0;
    background: yellow;
    position: absolute;
    top: 25%;
    left: 50%;
    margin-right: -50%;
    transform: translate(-50%, -50%) }

</style>







