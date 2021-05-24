<template>
<div>

  <div class="mx-auto overflow-hidden main-header " height="100vh" flat>
    <v-system-bar height="30" color='#1f1f1c'></v-system-bar>
    <v-app-bar color="#393A3C" dark flat>
      <v-app-bar-nav-icon @click="drawer = !drawer"></v-app-bar-nav-icon>
      <!-- <template > -->
        <v-tabs align-with-title color="#fff">
          <v-spacer></v-spacer>
          <NuxtLink class="justify-center router-link" color="#fff"  to="/"><v-tab class="justify-center router-link">CHATS</v-tab></NuxtLink>
          <NuxtLink class="justify-center router-link" color="#fff"  to="/calls"><v-tab class="justify-center router-link">CALLS</v-tab></NuxtLink>
          <v-spacer></v-spacer>
          <NuxtLink class="justify-center router-link" to="/search"><v-icon class="pa-3">mdi-magnify</v-icon></NuxtLink>
        </v-tabs>
      <!-- </template> -->
    </v-app-bar>

    <v-navigation-drawer v-model="drawer" absolute  temporary>
    <div class="user-profile-picter">
      <v-card  dark height="150"  class="overflow-hidden ma-0 pa-0 rounded-0 ">
        <v-img height="100%"  src="https://picsum.photos/1920/1080?random"></v-img>
      </v-card>
      <div @click="show_useracounts = !show_useracounts" class="user-account-name pl-6 m-auto">
        <div>
          <div class="d-flex">
            <h5 class="justify-start">{{username}}</h5>
            <v-spacer></v-spacer>
            <v-icon class="justify-end ml-16 pt-1">mdi-chevron-down</v-icon>
          </div>
          <h6>{{user_tell}}</h6>
        </div>
      </div>

      </div>
      <v-list  nav danse>
        <span  :class="show_useracounts ? 'opacity-100' : 'opacity-0'">
        <v-list-item-group  v-for="(account,index) in user_acccount" :key="index" :class="['user-accounts',show_useracounts ? 'min-height' : '']" >
            <v-list-item-icon style="margin:0;" class="ma-0 pa-0">
                <v-img class="ml-2 user-account-avatars pa-0 ma-0" rounded width="40" height="40" src="https://picsum.photos/1920/1080?random"></v-img>
                <v-list-item-title class="user-account-username pa-0 ma-0 ml-1">{{account.name}}</v-list-item-title>
            </v-list-item-icon>
        </v-list-item-group>
        <v-list-item-group class="d-flex ml-3" :class="['user-accounts',show_useracounts ? 'min-height' : '']">
          <v-list-item-icon>
            <v-icon>mdi-plus</v-icon>
          </v-list-item-icon>
          <v-list-item-title class="user-account-username pa-0 ma-0 ml-1">Add Account</v-list-item-title>
        </v-list-item-group>
        </span>
      </v-list>
        <SIDEPANELITEMS></SIDEPANELITEMS>
      </v-navigation-drawer>
  </div>
</div>

</template>

<script>
import SIDEPANELITEMS from '@/components/header/SidePanelItem.vue'
export default({
  components:{
    SIDEPANELITEMS
  },
  data: () => ({
      drawer: false,
      group: null,
      show_useracounts:false,
      user_acccount:[
        {name:'mohammad Goudarzi1'},
        {name:'mohammad Goudarzi2'},
        {name:'mohammad Goudarzi3'},
      ],
      username:'Mohammad Goudarzi',
      user_tell:"+98 903 399 2048",
      items: [
        { title: 'Click Me' },
        { title: 'Click Me' },
        { title: 'Click Me' },
        { title: 'Click Me 2' },
      ],
    }),
    // this watch will close user accounts after closing side panel

    // watch: {
    //   drawer: function () {
    //     !this.drawer ? this.show_useracounts = false : "";
    //   },
    // },
})
</script>
<style lang="scss" scoped>
.main-header{
    width: 100%;
}
.user-profile-picter{
  position: relative;
  .user-account-name{
    position: absolute;
    margin-top:-44px;
    width: 100%;
    background-image: linear-gradient(to bottom, rgba(255,0,0,0), rgba(0,0,0,0.6));
  }
}
.router-link{
    text-decoration: none;
    color: #fff;
    display: inline-flex;
    letter-spacing: normal;
  }
  .user-account-avatars{
    border-radius: 50%;
  }
  .user-account-username{
    font-family: 16px !important;
  }
.user-accounts{
  max-height: 0px;
  overflow: hidden;
  transition-duration: 0.5s;
}
.min-height{
  max-height:50px !important;
  transition-duration: 0.3s;
}

.opacity-0{
    opacity: 0;
    transition: 0.01s;
}
.opacity-100{
    opacity: 1;
    transition: 2s;
}
</style>