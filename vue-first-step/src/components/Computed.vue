<template>
<h1>Computed</h1>
  <b>Date complète</b><br> {{date}}
  <br><br>
  <b>Date format DD-MM-YYYY</b> : br {{ddmmyyyy}}
  <br><br>
  <b>Heure au format HH:MM:SS</b> : <br> {{hhmmss}}

  <div>
    Name <br>
    <input type="text" v-model="name"><br>
    <ul style="list-style-type: none; margin-left: -40px;">
      <li v-for="name in found" style="">
        {{name}}

      </li>
    </ul>
  </div>
</template>

<script>
export default {
  name: "Computed",
  data() {
    return {
      date : new Date(),
      name : "",
      names : [
          "Aaron abbott",
          "Abe Adams",
          "Abraham adamson",
        "Adélaïde",
        "Adèle",
        "Adeline",
        "Adriana",
        "Agathe",
        "hAgnès",
        "Aïca",
        "Alaïs",
        "Albane",
        "Alex",
        "Alexandra",
        "Alexia",
        "Alice",
        "Alicia",
        "Aline",
        "Alison",
        "Alissa",
        "Alissia",
        "Alix",
        "Alizée",
        "Alyssa",
        "Alyssia",
        "Amandine",
        "Amber",
        "Ambre",
        "Amélie",
        "Anabelle",
        "Anaelle",
        "Anaïs",
        "Anceline",
        "Andréa",
        "Angelina",
        "Angèle",
        "Anne",
        "Anouck",
        "Ariane",
        "Ariella",
        "Arielle",
        "Armelle",
        "Assia",
        "Astride",
        "Aude",
        "Audrey",
        "Aurélia",
        "Aurore",
        "Ava",
        "Axelle",
        "Aziza",
      ]
    }
  },
  methods : {
    created() {
      setInterval(()=> {
        this.date = new Date();
      }, 1000);
    },
  },
  computed: {
    found() {
    return this.names.filter((name)=> {
      return name.toUpperCase().indexOf(this.name.toUpperCase()) !== -1;
    });
    },

    hhmmss() {
      return this.date.toTimeString().split(" ")[0]
    },
    ddmmyyyy() {
      let day = this.date.getDate();
      let month = this.date.getMonth();
      let year = this.date.getFullYear();
      if (day < 10 ) day = "0" + day;
      if (month < 10) month = "0" + month;
      return `${day}-${month}-${year}`;
    }
  }
}
</script>

<style scoped>

</style>