<template>
  <h1>Event</h1>


<div v-bind = "created()">Il est {{time}}</div>

  <div>
    <b>Message (avec v-model)</b> :
    <br><br>
    <input type="text" v-model="message">
    <br><br>
    <br><br>
    <b>Message du v-model</b> :
    <p>{{message}}</p>
  </div>


</template>

<script>


export default {
  name: "Event",
  data() {
    return {
      elements: [
        {text: "Element 1", modifyOn: false},
        {text: "Element 2", modifyOn: false},
        {text: "Element 3", modifyOn: false},
        {text: "Element 4", modifyOn: false},
        {text: "Element 5", modifyOn: false},
      ],
      show: false,
      message : '',
      time : "..."

    }
  },

  methods: {
    created() {
      setInterval(()=> {
        this.time = (new Date()).toTimeString().split(" ")[0];
      }, 1000)

    }

  }

}

</script>

<style scoped>
div {
  color: aliceblue;
}
</style>