<template>
  <div >
    <!-- <img alt="Vue logo" src="../assets/logo.png"> -->
    <div class="index-category">
      <div class="category" v-for="(list,i) in lists" :key="i">
        <i class="iconfont" :class="list.icon" :style="{background:list.color}" ></i>
        <label>{{list.title}}</label>
      </div>
    </div>
    <div class="banner">
      <img alt="Vue logo" v-for="(v,i) in imgArr" :key="i" :src="v" v-show="n==i">
      <div class="banner-circle">
        <ul>
          <li v-for="(v,i) in imgArr" :key="i" :class="n==i ? 'selected':''" ></li>
        </ul>
      </div>
    </div>
  </div>
</template>

<script>

export default {
  name: 'Home',
  data(){
    return {
      n:0,
      timer:null,
      lists:[
        {title:'美食',icon:'icon-history',color:'#f60'},
        {title:'礼品',icon:'icon-gift',color:'#2a5caa'},
        {title:'日历',icon:'icon-calculator',color:'#007d65'},
        {title:'视频',icon:'icon-play',color:'#ff00aa'},
        {title:'层级',icon:'icon-integral',color:'#f173ac'},
        {title:'声音',icon:'icon-voice',color:'#2468a2'},
        {title:'电子',icon:'icon-electronics',color:'#ef4136'},
        {title:'循环',icon:'icon-exchangerate',color:'#6f599c'}
      ],
      imgArr:[
        require('../assets/img/1.jpg'),
        require('../assets/img/2.jpg'),
        require('../assets/img/3.jpg'),
        require('../assets/img/4.jpg'),
        require('../assets/img/5.jpg'),
        require('../assets/img/6.jpg')
      ]
    }
  },
  methods:{
    play(){
      this.timer = setInterval(this.autoPlay,2500)
    },
    autoPlay(){
      this.n++;
      if (this.n==this.imgArr.length){
        this.n=0;
      }
    }
  },
  mounted() {
    this.play();
  },
  destroyed() {
    clearInterval(this.timer);
  }
}
</script>
