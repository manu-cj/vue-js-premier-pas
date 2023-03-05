<template>
  <Menu/>

</template>

<script>
import Menu from "@/components/Menu";
import pokemon from "../database/pokemon"

export default {
  name: 'App',
  components: {
    Menu,
    pokemon

  }
}
</script>

<style>
body {
  background-color: #494949;

}

#app {
  width: 100%;


}
</style>
