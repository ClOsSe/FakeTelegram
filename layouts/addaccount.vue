<template>
  <v-app > 
    <AddAccHeader></AddAccHeader>
    <Nuxt />
  </v-app>
</template>

<script>
import AddAccHeader from "../components/AddAccHeader/index"
export default {
  name:'addaccount.vue',
  components:{
    AddAccHeader
  },
}
</script>
<style lang="scss" scoped>

</style>