<template>
    <div class="container my-1">
        <ul class="list-group">
            <p class="list-group-item">Name : {{ unName }}</p>
            <p class="list-group-item">Age : {{ unAge }}</p>
        </ul>
  </div> 
</template>

<script setup lang='js'>
import { defineProps } from 'vue';

const props = defineProps({
  unName: {
    type: String,
    required: true
  },
  unAge: {
    type: String,
    required: true
  },
});

</script>