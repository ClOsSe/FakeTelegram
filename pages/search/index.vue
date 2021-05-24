<template>
    <div>
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

</style>
