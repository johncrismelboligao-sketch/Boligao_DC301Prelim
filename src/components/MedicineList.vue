<script setup>
defineProps({
  patientName: String,
  patientId: String,
  room: String,
  doctor: String
})
</script>

<style scoped>
.card{
  border:1px green;
  padding:15px;
  margin-bottom:20px;
}
</style>

<template>
  <div class="card">
    <h2>Patient Profile</h2>

    <p><strong>Patient Name:</strong> {{ patientName }}</p>
    <p><strong>Patient ID:</strong> {{ patientId }}</p>
    <p><strong>Room:</strong> {{ room }}</p>
    <p><strong>Doctor:</strong> {{ doctor }}</p>
  </div>
</template>

