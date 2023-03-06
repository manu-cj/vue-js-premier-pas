<template>
  <div class="card">
    <div class="fiche-pokemon" v-for="poke in pokemon">
      <div class="pokemon-data">
        <ul>
          <li>
            <h1 class="pokemon-number-pokedex"> {{ poke.number }}</h1>
          </li>
          <li>
            <h1 class="pokemon-name"> {{ poke.name }}</h1>
          </li>
          <li>
            <h3 class="pokemon-name">Type : {{ poke.type }}</h3>
          </li>
        </ul>
        <div class="display">
          <div class="img"><img :src="poke.url" alt=""></div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>


export default {

  data() {

    return {
      id: 0,
      pokemon: [
        {
          id: "0",
          number: "001",
          name: "Bulbizarre",
          type: "plante",
          url: "https://www.pokepedia.fr/images/thumb/e/ef/Bulbizarre-RFVF.png/250px-Bulbizarre-RFVF.png"
        },
        {
          id: "1",
          number: "002",
          name: "Herbizarre",
          type: "plante",
          url: "https://www.pokepedia.fr/images/4/44/Herbizarre-RFVF.png"
        },
        {
          id: "2",
          number: "003",
          name: "Florizarre",
          type: "plante",
          url: "https://www.pokepedia.fr/images/thumb/4/42/Florizarre-RFVF.png/1200px-Florizarre-RFVF.png"
        },
      ],

      image: "https://www.pokepedia.fr/images/thumb/4/42/Florizarre-RFVF.png/1200px-Florizarre-RFVF.png"
    }
  },



}

</script>

<style scoped>
.card {
  margin: 50px;
  width: 20%;
  height: 450px;
  display: flex;
  flex-direction: column;
  justify-content: space-around;
  flex-wrap: wrap;
  align-items: center;
  justify-items: center;
}

.fiche-pokemon {
  margin: 50px;
  width: 80%;
  height: 400px;
  display: flex;
  flex-direction: column;
  justify-content: flex-start;
  align-items: center;

  /* From https://css.glass */
  background: rgba(0, 255, 115, 0.7);
  box-shadow: 0 8px 32px 0 rgb(132, 255, 0);
  backdrop-filter: blur( 1px );
  -webkit-backdrop-filter: blur( 1px );
  border-radius: 20px;
  border: 1px solid rgba( 255, 255, 255, 0.18 );
}

.fiche-pokemon:hover {
  margin: 50px;
  width: 100%;
  height: 450px;
  box-shadow: 0 8px 32px 0 rgb(255, 98, 0);
  transition-duration: 220ms;
}

.pokemon-data {
  width: 100%;
  height: 25%;
  margin: 50px;
}

.pokemon-name, .pokemon-type {
  display: flex;
  justify-content: space-around;
}
li {
  list-style-type: none;
}
.display {
  width: 100%;
  display: flex;
  justify-content: space-around;
  align-items: center;
}

.img img {
  width: 60%;
  height: 200px;
  margin: 25%;
}

.arrow {
  width: 20%;
}

.arrow-left, .arrow-right {
  width: 100%;
  height: 100px;
  font-size: 30px;
  color: #00f699;
  display: flex;
  justify-content: center;
  align-items: center;
  border-radius: 45%;
  border: 5px solid #ea4e00;
  cursor: pointer;
  background: rgb(255, 98, 0);
  box-shadow: 0 4px 30px rgba(0, 0, 0, 0.1);
  backdrop-filter: blur(15px);
  -webkit-backdrop-filter: blur(5px);
}
</style>