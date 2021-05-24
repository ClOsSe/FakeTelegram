<template>
<div>
  <div class="mx-auto overflow-hidden main-header " height="100vh" flat>
    <v-system-bar height="30" color='#121212'></v-system-bar>
    <v-app-bar color="#1E1E1E" class="d-flex" height="57px" dark flat>
        <div class="nav-parent d-flex">
        <NuxtLink class="router-link" to="/"><v-icon >mdi-arrow-left</v-icon></NuxtLink>
        <h4 class="ml-5 title">Add Account</h4>
        </div>
    </v-app-bar>
  </div>
</div>

</template>

<script>
export default ({
    

})
</script>
<style lang="scss" scoped>
.main-header{
    width: 100%;
}
.router-link{
    text-decoration: none;
    color: #fff;
    display: inline-flex;
    letter-spacing: normal;
}
.title{
    font-size: 15px;
}
 
</style>