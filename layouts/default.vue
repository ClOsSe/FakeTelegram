<template>
  <v-app> 
    <Header></Header>
    <nuxt />
  </v-app>
</template>

<script>
import Header from "../components/header/index"
export default {
  name:'default.vue',
  components:{
    Header
  },
}
</script>
