
<script setup>
defineProps({
  patientName: String,
  patientId: String,
  medicines: Array
})
</script>

<style scoped>
.card{
  border:1px green;
  padding:15px;
  margin-top:20px;
}
</style>
<template>
  <div class="card">
    <h2>Medicine List</h2>

    <p><strong>Patient Name:</strong> {{ patientName }}</p>
    <p><strong>Patient ID:</strong> {{ patientId }}</p>

    <ul>
      <li v-for="medicine in medicines" :key="medicine">
        {{ medicine }}
      </li>
    </ul>
  </div>
</template>

