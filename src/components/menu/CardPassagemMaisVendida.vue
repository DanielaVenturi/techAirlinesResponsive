<script setup>
import { listaMenu } from '@/components/menu/ListaMenu.js'
import MButton from '@/components/MButton.vue';

</script>
<template>

<section>
  <div class="card-passagensMenu" v-for="lista in listaMenu" :key="lista.id">
    <div class="informacao-passagem">
      <div class="wrap-passagens">
        <img :src="lista.img" alt="foto" class="foto-passagem" />
      </div>
      <p class="title">{{ lista.title }}</p>
      <p class="origin">Origem: {{ lista.origin }}</p>
      <p class="destiny">Destino: {{ lista.destiny }}</p>
    </div>
    <div class="mb-button">
      <MButton @click="$router.push({name: 'passagem', params: { id: lista.id }})"></MButton>
    </div>
  </div>
</section>
  
</template>


<style scoped>
section{
display: flex;
justify-content: center;
  flex-direction: row;
  flex-wrap: wrap;
}


.card-passagensMenu {
  background-color: rgba(50, 83, 168, 0.63);
  /*margin: 25px 65px;*/
    padding: 10px;
  border-radius: 10px;
  width:15vw;
  margin: 2vw 3vw;
  color: rgba(255, 255, 255, 1);
  color: #fff;
  
  font-weight: 400;
}

.card-passagensMenu .title {
  margin-bottom: 1px;
  /*font-size: xx-large;*/
  font-size: 0.9em;
}

.foto-passagem {
  width: 100%;
  /*max-height: 100%;*/
  border-radius: 10px;
}

.wrap-passagens {
  display: flex;
  justify-content: center;
  align-items: center;
  background-color: white;
  border-radius: 10px;
  width:15vw;
  height: 15vw;
  overflow: hidden;
  /*height:40vw;*/
}

.wrap-passagens img {
  width: 100%;
  height: auto;
}


.informacao-passagem .origin, .informacao-passagem .destiny{
  font-size: 0.6em;
}

@media only screen and (max-width: 480px) {
   section{
        display: block;
    }
    .card-passagensMenu{
      width:80vw;
      margin: 0 8vw;
    }
    .wrap-passagens{
      width: 80vw;
    }
}

@media only screen and (max-width: 1300px) {
  .card-passagensMenu .title {
  /*font-size: xx-large;*/
  font-size: 0.7em;
}
.informacao-passagem .origin, .informacao-passagem .destiny{
  font-size: 0.4em;
}


.card-passagensMenu{
      width:20vw;
      margin: 2vw 5vw;
    }
    .wrap-passagens{
      width: 20vw;
    }
}
</style>
