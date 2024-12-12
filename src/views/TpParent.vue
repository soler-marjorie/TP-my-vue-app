<template>
    <h1>TP props et Emit - 12/12/24</h1>
    <div>
        <activeUser
        :unName="name"
        :unAge="age"
        >

        </activeUser>

        <userData
        @ajout-infos="majInfos"
        >
        </userData>
    </div>
    
</template>

<script setup lang='js'>
import { ref, defineAsyncComponent } from 'vue';

const userData = defineAsyncComponent(() => import('../components/Communication/userDataYellow.vue')) ;
const activeUser = defineAsyncComponent(() => import('../components/Communication/activeUserBlue.vue')) ;

// Données réactives dans le Parent
let name =ref('');
let age = ref('');

const majInfos = (nouveauNom, nouvelAge) => {
    name.value = nouveauNom; // Mise à jour du nom
    age.value = nouvelAge;  // Mise à jour de l'âge
};

</script>