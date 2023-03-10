<template>
<!--  <Menu/>-->
<List/>
  <Event/>
</template>

<script>
// import Menu from "@/components/Menu";
import List from "@/components/List";
import Event from "@/components/Event";

export default {
  name: 'App',
  components: {
    // Menu,
     List,
    Event
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
