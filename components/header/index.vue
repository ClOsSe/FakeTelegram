<template>
  <v-card
    class="mx-auto overflow-hidden main-header"
    height="800px"
    flat
  >
    <v-system-bar
        height="30"
        color='#1f1f1c'
    ></v-system-bar>
    <v-app-bar
      color="#393A3C"
      dark
      flat
    >
      <v-app-bar-nav-icon @click="drawer = true"></v-app-bar-nav-icon>
      <template >
        <v-tabs align-with-title color="#fff">
          <v-tab class="justify-center">CHATS</v-tab>
          <v-tab class="justify-center">CALLS</v-tab>
          <v-spacer></v-spacer>
          <v-icon class="pa-3">mdi-magnify</v-icon>
        </v-tabs>
      </template>
    </v-app-bar>

    <v-navigation-drawer
      v-model="drawer"
      absolute
      temporary
    >
    <v-card  dark height="150"  class="overflow-hidden ma-0 pa-0 rounded-0">
      <v-img height="100%"  src="https://picsum.photos/1920/1080?random"></v-img>
    </v-card>
      <v-list
        nav
        dense
      >
        <v-list-item-group
          v-model="group"
          active-class="deep-purple--text text--accent-4"
        >
          <v-list-item>
            <v-list-item-icon>
              <v-icon>mdi-home</v-icon>
            </v-list-item-icon>
            <v-list-item-title>Home</v-list-item-title>
          </v-list-item>

          <v-list-item>
            <v-list-item-icon>
              <v-icon>mdi-account</v-icon>
            </v-list-item-icon>
            <v-list-item-title>Account</v-list-item-title>
          </v-list-item>
        </v-list-item-group>
      </v-list>
    </v-navigation-drawer>
  </v-card>
</template>

<script>

export default({
  data: () => ({
      drawer: false,
      group: null,
    }),
})
</script>
<style lang="scss" scoped>
.main-header{
    width: 100%;
    max-width: 480px;
}
</style>