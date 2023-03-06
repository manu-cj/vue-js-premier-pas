<template>
  <div>
    <ul>
      <li @dblclick="modify(index)" v-for="(element, index) in elements">
        <span style="width: 100px" v-if="!element.modifyOn"
        @dblclick="modify(index)">
           {{element.text}}
        </span>
        <input v-else
               v-bind:value="element.text"
               v-on:keyup.enter="valid(index, $event)"
               ref="input"
               type="text" style="width: 100px">
        <button @click="remove(index)" style="margin-left: 10px">delete</button>
      </li>
    </ul>
    <div v-if="elements.length === 0">
      <h1>Non, il n'y a plus rien ici</h1>
      <input type="text" style="width: 100px">
    </div>
  </div>
</template>

<script>


export default {
  name: "List",
  data() {
    return {
      elements: [
        {text : "Element 1", modifyOn : false},
        {text : "Element 2", modifyOn : false},
        {text : "Element 3", modifyOn : false},
        {text : "Element 4", modifyOn : false},
        {text : "Element 5", modifyOn : false},

      ]
    }
  },

  methods: {
    remove(index) {
     this.elements.splice(index, 1)
    },

    modify(index) {
      this.elements[index].modifyOn = true
    },

    valid(index, event) {
        this.elements[index].text = event.target.value;
        this.elements[index].modifyOn = false
    },

  },
  updated() {
    let inputs = this.$refs.input;
    if (inputs && inputs.length) {
      let last_input = inputs[inputs.length -1];
      last_input.focus();
    }
  },
}
</script>

<style scoped>
  div {
    color: aliceblue;
    font-size: 35px;
  }
</style>