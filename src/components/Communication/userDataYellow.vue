<template>
    <div class="container bg-info my-1">
        <h1>Formulaire d'édition</h1>
        <form @submit.prevent="submitData">
        <div class="mb-3">
            <label for="exampleFormControlInput1" class="form-label">Name</label>
            <input v-model="enteredName" class="form-control form-control-sm" type="text" placeholder="votre nom" aria-label=".form-control-sm example">
        </div>
        <div class="mb-3">
            <label for="exampleFormControlInput1" class="form-label">Age</label>
            <input v-model="enteredAge" class="form-control form-control-sm" type="number" placeholder="Votre age" aria-label=".form-control-sm example">
        </div>            
        <button class="btn btn-primary btn-sm col-12 my-1" @click="submitData()">MAJ des données</button>
        </form>
    </div>
</template>

<script setup lang='js'>
import { ref, defineEmits } from 'vue'

const enteredName = ref('');
const enteredAge = ref('');

const emit = defineEmits(['ajout-infos']);


const submitData = () => {
    emit('ajout-infos', enteredName.value, enteredAge.value);
}
</script>