<template>
<div>
  <div class="mx-auto overflow-hidden main-header " height="100vh" flat>
    <v-system-bar height="30" color='#121212'></v-system-bar>
    <v-app-bar color="#1E1E1E" class="d-flex" height="57px" dark flat>
        <div class="nav-parent d-flex">
        <NuxtLink class="router-link" to="/"><v-icon >mdi-arrow-left</v-icon></NuxtLink>
        <v-row>
            <v-col>
                <div class="mt-7" >
                    <v-text-field class="custom"  flat solo placeholder="Search" ></v-text-field>
                </div>    
            </v-col>
        </v-row>
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

 
</style>