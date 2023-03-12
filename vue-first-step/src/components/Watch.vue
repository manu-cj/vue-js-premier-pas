<template>
  <b>Texte (max 5 car)</b><br>
  <input type="text" v-model="text"><br><br>

<b>Text saisi</b><br>
  <h1>{{text}}</h1>
  <div style="color: #ea4e00" v-show="error">Maximum 5 caractère bouseux !</div>
</template>

<script>
export default {
  name: "Watch",
  data() {
    return {
      text : "Robert",
      error : false,
    }
  },
  watch : {
    text(newValue, oldValue) {
      if (newValue.length >= 7) {
        this.text = oldValue;
        this.error = true;
      }
      else if (newValue.length < 6) this.error = false
    }
  }
}
</script>

<style scoped>

</style>