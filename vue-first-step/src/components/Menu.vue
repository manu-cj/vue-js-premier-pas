<template>
  <div class="fiche-pokemon">
    <div class="arrow-left">
      <button v-if="id > 0" @click="id--">gauche</button>
    </div>

    <div class="pokemon-data">
      <ul>
        <li v-if="id >= 0">
         <h1> {{namesPokemon[id].name}}</h1>
        </li>
        <li v-else-if="id < 0">
          Aucun pokemon
        </li>
        <li v-else-if="id > 2">
          Aucun pokemon
        </li>
        <li v-if="id >= 0">
          <h3>Type : {{namesPokemon[id].type}}</h3>
        </li>
        <li v-if="id >= 0">

          <div class="img"><img :src="pokemon[id].url" alt=""></div>
        </li>
      </ul>
    </div>
    <div class="arrow-right">
      <button v-if="id < 2"  @click="id++">droite</button>
    </div>
  </div>
  <img src="" alt="">
</template>

<script>




const pokemon = [
  {
    id: "0",
    name: "Bulbizarre",
    type: "plante",
    url: '"https://www.pokepedia.fr/images/thumb/e/ef/Bulbizarre-RFVF.png/250px-Bulbizarre-RFVF.png"'
  },
  {
    id: "1",
    name: "Herbizarre",
    type: "plante",
    url: "https://www.pokepedia.fr/images/4/44/Herbizarre-RFVF.png"
  },
  {
    id: "2",
    name: "Florizarre",
    type: "plante",
    url: "https://www.pokepedia.fr/images/thumb/4/42/Florizarre-RFVF.png/1200px-Florizarre-RFVF.png"
  },
]


export default {

  data() {

    return {
      namesPokemon: pokemon,
      id : 0,
      pokemon : [
        {
          id: "0",
          name: "Bulbizarre",
          type: "plante",
          url: "https://www.pokepedia.fr/images/thumb/e/ef/Bulbizarre-RFVF.png/250px-Bulbizarre-RFVF.png"
        },
        {
          id: "1",
          name: "Herbizarre",
          type: "plante",
          url: "https://www.pokepedia.fr/images/4/44/Herbizarre-RFVF.png"
        },
        {
          id: "2",
          name: "Florizarre",
          type: "plante",
          url: "https://www.pokepedia.fr/images/thumb/4/42/Florizarre-RFVF.png/1200px-Florizarre-RFVF.png"
        },
      ],

      image:  "https://www.pokepedia.fr/images/thumb/4/42/Florizarre-RFVF.png/1200px-Florizarre-RFVF.png"
    }
  },



}

</script>

<style scoped>

.fiche-pokemon {
  width: 75%;
  height: 500px;
  border-radius: 25%;
  border-color: #2c3e50;
  background-color: aqua;
  display: flex;
  justify-content: space-around;
  align-items: center;
}

.img img {
  width: 100%;
  height: 200px;
}
</style>