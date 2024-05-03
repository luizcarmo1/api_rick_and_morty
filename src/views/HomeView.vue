<script setup>
  import { onMounted, reactive, ref} from 'vue';
  import PersonagensInfos from '../components/PersonagensInfos.vue'

  let personagens = reactive(ref());

  onMounted(() => {
      fetch("https://rickandmortyapi.com/api/character")
      .then(response => response.json())
      .then(response => {
        personas.value = response.results
        console.log(personas)
      })
    })
</script>

<template>
  <main>
    <div class="container">
      <div class="row mt-4">
        <div class="col-sm-12 col-md-6">
          <div class="card" style="width: 100%;">
            <div class="card-body row">
              <PersonagensInfos
                v-for="persona in personas"
                :key="persona.name"
                :name="persona.name"
                :url="persona.url"
                :status="persona.status"
                :species="persona.species"
                :gender="persona.gender"
                :location="persona.location"
                :episode="persona.episode"
                />
            </div>
          </div>
        </div>
      </div>
    </div>
  </main>
</template>
