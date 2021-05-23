<template>
   <v-card width="100%">
     <v-app>
      <v-card v-show="PinToTop" class="col-12 pa-0 ma-0" >
        <v-row  class="users-group-item pin-to-top col-12 d-flex ml-2 mt-2"  v-for="(item,index) in PinToTopList" :key="index" >
             <div class="col-2  pa-0">
               <v-img class="users-group-avatar justify-center " :src="item.avatarURL" ></v-img>
             </div>
             <div class="col-7 ma-0 pa-0 mt-2 ml-2">
               <div class="d-flex ">
                 <h4>{{item.title}}</h4>
                 <v-icon v-show="item.muted" class="icons">mdi-volume-variant-off</v-icon>
               </div>
               <div class="d-flex ma-0 pa-0">
                 <v-icon class="icons mt-1">{{item.mdiIcons}}</v-icon>
                 <p>{{item.content}}</p>
               </div>
             </div>
             <div class="col-2 ma-0 pa-0 information-date">
               <p class="ma-0 pa-0 date">{{item.date}}</p>
                 <v-badge class="ma-0 pa-0" bottom  :color="item.muted ? '#999999' : 'primary'" content="10"></v-badge>
             </div>
        </v-row>
      </v-card>
      <v-card class="col-12 pa-0 ma-0 mt-2">
        <v-row  class="users-group-item  col-12 d-flex ml-2 mt-2" v-for="(item,index) in contact" :key="index">
        <div class="col-2  pa-0">
          <v-img class="users-group-avatar justify-center " :src="item.avatarURL" ></v-img>
        </div>
        <div class="col-7 ma-0 pa-0 mt-2 ml-2">
          <div class="d-flex ">
            <h4>{{item.title}}</h4>
            <v-icon v-show="item.muted" class="icons">mdi-volume-variant-off</v-icon>
          </div>
          <div class="d-flex ma-0 pa-0">
            <v-icon class="icons mt-1">{{item.mdiIcons}}</v-icon>
            <p>{{item.content}}</p>
          </div>
        </div>
        <div class="col-2 ma-0 pa-0 information-date">
          <p class="ma-0 pa-0 date">{{item.date}}</p>
            <v-badge class="ma-0 pa-0" bottom  :color="item.muted ? '#999999' : 'primary'" content="10"></v-badge>
        </div>
        
      </v-row>
      <div class="justify-center d-flex">
            <h3 class="number-of-chats ml-1 mr-1">{{AllChats}}</h3>
            <h3 class="number-of-chats ml-1 mr-1">chats</h3>
        </div>
      </v-card >
      
     </v-app>
   </v-card>
</template>

<script>

export default {
  data(){
    return{
      PinToTop:true,
      AllChats:null,
      PinToTopList:[
        { 
          index:0,
          avatarURL:"https://picsum.photos/1920/1080?random",
          title:'kaf',
          content:'نگو پول نگو تحصیلات ',
          date:'Wed',
          unReadMessage:10,
          muted:false,
          mdiIcons:'mdi-camera'
        },
        { 
          index:1,
          avatarURL:"https://picsum.photos/1920/1080?random",
          title:'programers',
          content:'most important things',
          date:'Tue',
          unReadMessage:10,
          muted:false,
          mdiIcons:'mdi-music-note'
        },
        { 
          index:2,
          avatarURL:"https://picsum.photos/1920/1080?random",
          title:'Family',
          content:'salam be hame',
          date:'Tue',
          unReadMessage:10,
          muted:false,
          mdiIcons:'mdi-video'
        }
      ],
      contact:[
        { 
          index: 0,
          avatarURL:"https://picsum.photos/1920/1080?random",
          title:'Musix',
          content:'ahang jadid shadmehr aghili ',
          date:'4 Aug 2020',
          unReadMessage:10,
          muted:true,
          mdiIcons:'mdi-account-multiple'
        },
        { 
          index: 1,
          avatarURL:"https://picsum.photos/1920/1080?random",
          title:'Telegram',
          content:'hello',
          date:'7 May',
          unReadMessage:10,
          muted:false,
          mdiIcons:'mdi-account-multiple'
        },
        { 
          index: 2,
          avatarURL:"https://picsum.photos/1920/1080?random",
          title:'Movie',
          content:'topgun',
          date:'today',
          unReadMessage:10,
          muted:false,
          mdiIcons:'mdi-account-multiple'
        },
        { 
          index: 3,
          avatarURL:"https://picsum.photos/1920/1080?random",
          title:'Telegram',
          content:'hello',
          date:'7 May',
          unReadMessage:10,
          muted:false,
          mdiIcons:'mdi-video'
        },
      ]
    }
  },
  mounted(){
    this.SumOfAllChats();
  },
  methods:{
    SumOfAllChats()
    {
      var counter = 0;
      for(var i in this.contact){counter ++;}
      this.AllChats = counter;
      counter = 0;
      for(var j in this.PinToTopList){counter ++;}
      this.AllChats +=counter;
    }
  },
  components: {
  }
}
</script>
<style lang="scss" scoped>
.icons {
  width: 20px;
  height: 20px;
  margin: 0px 5px 0 5px;
  opacity: 0.5;
}
.number-of-chats{
  color: darkgray;
}
.users-group-item{
  width: 100%;
  .users-group-avatar{
    width: 62px;
    height: 62px;
    border-radius: 50%;
  }
  .information-date{
    justify-content: center;
    text-align: center;
    .date{
      font-size: 12px;
      color:darkgray
    }
  }
}
</style>
