<template>
  <div class="container">
    <h1>Hospital Patient Monitoring System</h1>

    <img
      src="https://thumbs.dreamstime.com/b/hospital-building-modern-parking-lot-59693686.jpg"
      alt="Hospital"
      width="350"
    >

    <PatientProfile
      :patientName="patientName"
      :patientId="patientId"
      :room="room"
      :doctor="doctor"
    />

    <h2>Patient Status</h2>

    <p :class="{ admitted: status, discharged: !status }">
      {{ status ? "Admitted" : "Discharged" }}
    </p>

   
    <h2>Checkups: {{ checkups }}</h2>

    <button @click="addCheckup">
      Add Checkup
    </button>

    <button @click="removeCheckup">
      Remove Checkup
    </button>

 
    <MedicineList
      :patientName="patientName"
      :patientId="patientId"
      :medicines="medicines"
    />

    <h2>Classification</h2>

    <p>{{ classification }}</p>

  </div>
</template>

<script setup>
import { ref, computed } from 'vue'
import PatientProfile from './components/PatientProfile.vue'
import MedicineList from './components/MedicineList.vue'

const patientName = "Borny James"
const patientId = "Q-11"
const room = "Room 211"
const doctor = "Dr. James"

const checkups = ref(0)

const status = ref(true)

const medicines = ref([
  "Biogekiss",
  "Amoxicillin",
  "Vitamin C",
  "Ibuprofen",
  "Omeprazole"
])

function addCheckup() {
  checkups.value++
}

function removeCheckup() {
  if (checkups.value > 0) {
    checkups.value--
  }
}

const classification = computed(() => {
  return medicines.value.length >= 5
    ? "Stable"
    : "Critical"
})
</script>

<style>
.container{
  font-family: Arial, sans-serif;
  padding:20px;
}

button{
  margin-right:10px;
  margin-bottom:20px;
  padding:8px 12px;
}

.admitted{
  color:green;
  font-weight:bold;
}

.discharged{
  color:red;
  font-weight:bold;
}

img{
  margin-bottom:20px;
}
</style>
images.unsplash.com