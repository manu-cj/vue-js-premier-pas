<template>
  <h1>Event</h1>
  <div id="menu" style=" position: absolute; border: solid 1px red; background-color: #ddd;" v-show="show">
    <ul>
      <li v-for="element in elements">{{ element.text }}</li>
    </ul>
  </div>
  <button @click="click($event)" style="font-size: 20px">Afficher la liste {{ x }} {{ y }}</button>
</template>

<script>
export default {
  name: "Event",
  data() {
    return {
      x: 0,
      y: 0,
      elements: [
        {text: "Element 1", modifyOn: false},
        {text: "Element 2", modifyOn: false},
        {text: "Element 3", modifyOn: false},
        {text: "Element 4", modifyOn: false},
        {text: "Element 5", modifyOn: false},
      ],
      show: false,
    }
  },

  methods: {
    click(event) {
      let menu = document.querySelector("#menu");
      menu.style.left = event.pageX + 'px';
      menu.style.top = event.pageY + 'px';
      menu.style.backgroundColor = 'red';
      this.show = true;
    }


  }
}
</script>

<style scoped>

</style>