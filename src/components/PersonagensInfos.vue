<script setup>
defineProps(["id", "name", "image", "status", "species", "gender", "location", "episode"])
</script>


<template>
    <div class="col-md-4">
        <div class="card mb-3">
            <img :src="image" :alt="name" class="card-img-top mt-3">
            <p class="text-center mt-2 fs-3">{{ name }}</p>
            <div class="card-body">
                <p class="card-text">
                    <strong>Status:</strong> <br>
                    {{ status }} <br>
                    <strong>Especie:</strong> <br>
                    {{ species }} <br>
                    <strong>Genero:</strong> <br>
                    {{ gender }} <br>
                    <strong>Localizacao:</strong> <br>
                    {{ location }}  <br>
                    <strong>Total de Episodios:</strong> <br>
                    {{ episode.length }} <br>
                </p>
            </div>
        </div>
    </div>
</template>