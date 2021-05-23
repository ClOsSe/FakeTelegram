<template>
    <div>
        <v-row class="d-block" v-for="(item,index) in CallsList" :key="index">
            <h3 class="date pa-2 ma-2">{{item.date}}</h3>
            <v-card class="ml-2 mr-2 pa-0">
                <v-row class="pa-1">
                    <div class="col-2 pa-0">
                        <v-img height="62" width="62" class="avatar" :src="item.avatarURL"></v-img>
                    </div>
                    <div class="col-7 content-parent d-flex">
                        <h4>{{item.username}}</h4>
                        <v-icon :color="item.status != 'Canceled' ? 'success' : 'red'" >{{item.mdiIcons}}</v-icon>
                    </div>
                    <div class="col-2 ma-0 pa-0">
                        <p>{{item.time}}</p>
                    </div>
                </v-row>
            </v-card>
        </v-row>
    </div>
</template>
<script>

export default ({
    data(){
        return{
            CallsList:[
                {
                    date: '2 March 2020',
                    avatarURL:'https://picsum.photos/1920/1080?random',
                    username:'Father',
                    status:'success',
                    statusCall:'Incoming',
                    mdiIcons:'mdi-arrow-bottom-left',
                    time:'15:00'
                },
                {
                    date: '13 March 2019',
                    avatarURL:'https://picsum.photos/1920/1080?random',
                    username:'mr.amiri',
                    status:'Canceled',
                    statusCall:'Canceled',
                    mdiIcons:'mdi-arrow-top-right',
                    time:'13:50'
                },
                {
                    date: '10 March 2019',
                    avatarURL:'https://picsum.photos/1920/1080?random',
                    username:'mr.davari',
                    status:'Canceled',
                    statusCall:'Outgoing',
                    mdiIcons:'mdi-arrow-top-right',
                    time:'10:16'
                },
                {
                    date: '9 March 2019',
                    avatarURL:'https://picsum.photos/1920/1080?random',
                    username:'mr.samadi',
                    status:'Canceled',
                    statusCall:'Missed',
                    mdiIcons:'mdi-call-missed',
                    time:'13:16'
                }

            ]
        }
    }
})
</script>
<style lang="scss" scoped>
.avatar{
    border-radius: 50%;
}
.date{
    font-size: 14px;
}
</style>