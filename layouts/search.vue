<template>
  <v-app > 
    <SearchHeader></SearchHeader>
    <Nuxt />
  </v-app>
</template>

<script>
import SearchHeader from "../components/searchHeader/index"
export default {
  name:'search.vue',
  components:{
    SearchHeader
  },
}
</script>
<style lang="scss" scoped>

</style>