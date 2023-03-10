<template>
  <div>
    <ul>
      <li v-for="(element, index) in elements">
        <span v-bind:style="{color : element.color}" style="width: 100px" v-if="!element.modifyOn"
        @dblclick="modify(index)">
           {{element.text}}
        </span>
        <input v-else
               v-bind:value="element.text"
               v-on:keyup.enter="valid(index, $event)"
               ref="input"
               type="text" style="width: 100px">
        <button @click="modify(index)" style="margin-left: 10px">modifier</button>
        <button @click="remove(index)" style="margin-left: 10px">delete</button>
      </li>
    </ul>
    <button v-if="addElement === false" @click="addElement = true" style="margin-left: 10px">add</button>
    <button v-if="addElement=== true"
            @click="addElement = false"
            style="margin-left: 10px">annuler</button>
    <input v-if="addElement === true"
           v-on:keyup.enter="add($event)"
           type="text" placeholder="Ajoutez un élément">
    <div v-if="elements.length === 0">
      {{addElement = null}}
      <h1>Oh non, il n'y a plus rien ici !</h1>
      <input v-on:keyup.enter="add($event)" type="text" placeholder="Ajoutez un élément">
    </div>
  </div>
</template>

<script>


export default {
  name: "List",
  data() {
    return {
      elements: [
        {text : "Element 1", modifyOn : false, color : "red"},
        {text : "Element 2", modifyOn : false, color : "yellow"},
        {text : "Element 3", modifyOn : false, color : "blue"},
        {text : "Element 4", modifyOn : false, color : "green"},
        {text : "Element 5", modifyOn : false, color : "brown"},
      ],
      addElement : false,
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

    add(event) {
      this.elements.push({text: event.target.value, modifyOn: false});
      this.addElement = false
    }

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
  }

  li {
    font-size: 35px;
  }
</style>