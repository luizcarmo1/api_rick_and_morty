<script setup>
    const persona = defineProps(["id", "name", "url", "status", "species", "gender", "location", "episode"])
    const idPersona = persona.url.split('/')[4]
    const imageUrl = "https://rickandmortyapi.com/api/character/" + idPersona + ".jpeg"
</script>


<template>
    <div class="col-md-4">
        <div class="card mb-3">
            <img :src="imageUrl" height="80" alt="..." class="card-img-top mt-3">
            <p class="text-center">{{ persona.name }}</p>
        </div>
    </div>
</template>