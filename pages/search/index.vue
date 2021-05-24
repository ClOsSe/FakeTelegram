<template>
    <div>
    <v-row class="d-block">
        <h3 class="title ma-2">People</h3>
        <v-card>
            <v-row class="d-flex pa-0 ma-0">
                <v-col class="d-block pb-1 pt-1 item"  v-for="(item,index) in PeopleList" :key="index">
                    <v-img height="65px" width="65px" class="avatar pa-0 ma-0" :src="item.avatarURL"></v-img>
                    <p class="username pa-0 ma-0">{{item.username}}</p>
                </v-col>
            </v-row>
        </v-card>
    </v-row>
    <v-row class="d-block mt-2">
        <h3 class="title ma-2">Recent</h3>
        <v-card v-for="(item,index) in RecentList" :key="index">
            <v-row >
                <v-col class="col-2 pa-1 ma-0">
                    <v-img class="avatar mt-1" height="65px" width="65px" :src="item.avatarURL"></v-img>
                </v-col>
                <v-col  class="col-7 pa-1 ma-0">
                    <div class="d-flex">
                        <h4 class="mt-1">{{item.username}}</h4>
                        <v-icon v-show="!item.muted" color="#999999" class="icons">mdi-volume-variant-off</v-icon>
                    </div>
                    <div class="d-flex mt-1">
                        <p  class="date">{{item.date}}</p>
                    </div>
                </v-col>
                <v-col class="offset-1"></v-col>
                <v-col  class="justify-center col-1 pa-1 ma-0" style="text-align:center;align-item:center">
                    <v-badge class="mt-11 justify-center" :color="item.muted ? 'primary' : '#999999'"  :content="item.unReadMessage" ></v-badge>
                </v-col>
            </v-row>
        </v-card>
    </v-row>

    </div>
</template>
<script>
export default ({
    layout:'search',
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
                {
                    date: '11:54',
                    avatarURL:'https://picsum.photos/1920/1080?random',
                    username:'Reza',
                    muted:true,
                    unReadMessage:1,
                }
            ],
            RecentList:[
                {
                    date: 'last seen recently',
                    avatarURL:'https://picsum.photos/1920/1080?random',
                    username:'Father',
                    muted:false,
                    unReadMessage:1,
                },{
                    date: '10:50',
                    avatarURL:'https://picsum.photos/1920/1080?random',
                    username:'Mr.Samadi',
                    muted:false,
                    unReadMessage:1,
                },{
                    date: '19 March 2019',
                    avatarURL:'https://picsum.photos/1920/1080?random',
                    username:'Mr.kharazmi',
                    muted:false,
                    unReadMessage:1,
                },
            ]
        }
    }
})
</script>
<style lang="scss" scoped>
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
.item{
    justify-content: center;
    align-items: center;
    text-align: center;
    max-width: 90px;
    .username{
        font-size: 12px;
    }
}

</style>
