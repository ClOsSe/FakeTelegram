<template>
  <v-app > 
    <Header></Header>
    <Nuxt />
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
<style lang="scss" scoped>

</style>