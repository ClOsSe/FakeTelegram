<template>
<div>
  <div class="mx-auto overflow-hidden main-header " height="100vh" flat>
    <v-system-bar height="30" color='#1f1f1c'></v-system-bar>

    <v-app-bar color="#393A3C" class="d-flex" height="57px" dark flat>
        <div class="nav-parent d-flex">
        <NuxtLink class="router-link" to="/"><v-icon >mdi-arrow-left</v-icon></NuxtLink>
        <v-row>
            <v-col>
                <div class="mt-7" >
                    <v-text-field placeholder="Search" outlined ></v-text-field>
                </div>    
            </v-col>
        </v-row>
            
        </div>
        
    </v-app-bar>

    <v-row class="d-block">
        <h3 class="title ma-2">People</h3>
        <v-card v-for="(item,index) in PeopleList" :key="index">
            <v-row >
                <v-col class="col-2 pa-1 ma-0">
                    <v-img class="avatar mt-1" height="65px" width="65px" :src="item.avatarURL"></v-img>
                </v-col>
                <v-col  class="col-7 pa-1 ma-0">
                    <h4 class="mt-1">{{item.username}}</h4>
                        <div class="d-flex mt-1">
                            <p  class="date">{{item.date}}</p>
                        </div>
                </v-col>
                <v-col class="offset-1"></v-col>
                <v-col  class="justify-center col-1 pa-1 ma-0" style="text-align:center;align-item:center">
                    <v-badge class="mt-11 justify-center"  :content="item.unReadMessage" ></v-badge>
                </v-col>
            </v-row>
        </v-card>
    </v-row>

   
  </div>
</div>

</template>

<script>
export default ({
    data(){
        return{
            PeopleList:[
               {
                    date: 'last seen recently',
                    avatarURL:'https://picsum.photos/1920/1080?random',
                    username:'Father',
                    muted:false,
                    unReadMessage:1,
                },
            ]
        }
    }

})
</script>
<style lang="scss" scoped>
.main-header{
    width: 100%;
}
.title{
    color: darkgray;
    font-size: 12px;
}
.avatar{
    border-radius: 50%;
}
.date{
    color: darkgray;
}
.router-link{
    text-decoration: none;
    color: #fff;
    display: inline-flex;
    letter-spacing: normal;
  }
</style>