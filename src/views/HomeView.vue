<script setup>
  import { onMounted, reactive, ref} from 'vue';
  import PersonagensInfos from '../components/PersonagensInfos.vue'

  let personas = reactive(ref());

  onMounted(() => {
      fetch("https://rickandmortyapi.com/api/character")
      .then(response => response.json())
      .then(response => {
        personas.value = response.results
      })
    })
</script>

<template>
  <main>
    <div class="container">
      <div class="row mt-4">
        <div class="col-sm-12">
          <div class="card" >
            <div class="card-body row">
              <PersonagensInfos
                v-for="persona in personas"
                :key="persona.name"
                :name="persona.name"
                :image="persona.image"
                :status="persona.status"
                :species="persona.species"
                :gender="persona.gender"
                :location="persona.location.name"
                :episode="persona.episode"
                />
            </div>
          </div>
        </div>
      </div>
    </div>
  </main>
</template>
