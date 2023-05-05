<template>
    <p class="text-center mb-3 dark:text-blue-300">Trabajos realizados <font-awesome-icon/></p>
    <div class="max-h-[50vh] overflow-auto sm:w-4/12 mx-auto">
        <Loader v-if="loading" />
        <div v-if="error" class="text-red-500 text-center">{{ error }}</div>
        <div v-for="(project) in projects" :key="project.id">
            <a :href="project.html_url" target="_bl">
                <div class="bg-blue-300 mb-4 p-2 rounded-md shadow-md">
                    <h2 class="font-bold text-xl">{{ project.name }}</h2>
                    <p>{{ project.description }}</p>
                </div>
            </a>
        </div>
    </div>
</template>
<script setup>
import { ref, onMounted } from 'vue';
import Loader from '../components/Loader.vue';

const projects = [
    {
        id: 1,
        name: "Proyecto de Diseño Web",
        html_url: "https://github.com/jmoprix/EComerce",
        description: "Es un Proyecto de diseño web del"
    },
    {
        id: 2,
        name: "Proyecto de Diseño Web II",
        html_url: "https://github.com/jmoprix/Dise-o-Web-II",
        description: "Es un Proyecto de Diseño Web II en el que se modificó un diseño clonado de git hub"
    },
    {
        id: 3,
        name: "Proyecto de Programacion III",
        html_url: "https://github.com/jmoprix/Juego",
        description: "Es un Proyecto de programacion en Python en el que se realizó un juego"
    },
    {
        id: 4,
        name: "Proyecto de Base de datos II",
        html_url: "https://app.powerbi.com/links/I-Gi50Z0Ra?ctid=cf263038-f11c-49d2-9183-556a34b747e2&pbi_source=linkShare&bookmarkGuid=6732b786-8265-4445-a203-ccc7006978b8",
        description: "Es un Proyecto de Base de datos utilizando una presentacion en Power Bi"
    },
];

const loading = ref(false);
const error = ref(null);

onMounted(async () => {
    
});

</script>
