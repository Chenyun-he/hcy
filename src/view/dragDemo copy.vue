<template> 
  <div class=""> 

  <!-- 左边列表 -->
  <div class="marquee-wrap">
    <ul class="marquee-list" :class="{'animate-up': animateUp}">
      <li v-for="(item, index) in listData" :key="index">{{item}}</li>
    </ul>
  </div> 

    <div class="sgx-wrap">
    <ul class="sgx-list" :class="{'sgx-up': sgxUp}">
      <li v-for="(item, index) in showData" :key="index">{{item}}</li>
    </ul>
  </div> 
   
  
  <img :src="backFirst" class="backFirst">
  <img :src="white" class="white">
  <img :src="backSecond" class="backSecond">
  <img :src="blue" class="blue">
  <img :src="pink" class="pink">
  <img :src="handsome" class="handsome">
  <img :src="you" class="you">
  <img :src="handsomeSay" class="handsomeSay">
  <img :src="youSay" class="youSay">
  <img :src="circle" class="circle">
  <img :src="homepage" class="homepage">
  <!-- 这是canBack页面
  <div @click = 'go'>点我跳转</div>
  <div @click = 'back'>点我返回</div> -->
  </div>
</template>



<script>
import backFirstDefault from '@/assets/picture/second/backFirst.png'
import whiteDefault from '@/assets/picture/second/white.png'
import backSecondDefault from '@/assets/picture/second/backSecond.png'
import blueDefault from '@/assets/picture/second/blue.png'
import pinkDefault from '@/assets/picture/second/pink.png'
import handsomeDefault from '@/assets/picture/second/handsome.png'
import youDefault from '@/assets/picture/second/you.png'
import handsomeSayDefault from '@/assets/picture/second/handsomeSay.png'
import youSayDefault from '@/assets/picture/second/youSay.png'
import circleDefault from '@/assets/picture/second/circle.png'
       
import homepageDefault from '@/assets/picture/second/homepage.png'
// 这是第一个
// 传递给子组件的值
export default{
  data() {
    return {
      backFirst:backFirstDefault,
      white:whiteDefault,
      backSecond:backSecondDefault,
      blue:blueDefault,
      pink:pinkDefault,
      handsome:handsomeDefault,
      you:youDefault,
      handsomeSay:handsomeSayDefault,
      youSay:youSayDefault,
      circle:circleDefault,
      homepage:homepageDefault,
      animateUp: false,
      sgxUp:false,
      value:0,
      showData:['','我家北京有5套房，有3辆车，这都看不上？','','我得好好完善自己啊，要学的东西太多啦，到时候跟你走一块也不配套啊。','','那你什么时候有空我们一起吃个饭或者去哪玩一下','','你好看的，但比我还差一点','','准备睡觉了，明天还要工作'],
      listData: ['在吗，我看书看到很晚了，想聊会', '','今晚本身哥们叫我去喝酒，叫了很多小姐姐。但不想理，只想跟你聊天。', '','最近准备乐理听音的考试，考完了就想去找你','','周末去吃饭吗，吃多少钱的都行，不差钱。','','互相关注一下呗，别人都是求着我才关注的。'],
      i:0,
      timer: null

    };
  },
  // setTimeout
  // setInterval（“方法名或方法”，“延时”）， 
  // 第一个参数为方法名或者方法，注意为方法名的时候不要加括号,第二个参数为时间间隔
  mounted() {
    // this.timer = setInterval(this.scrollAnimate, 2000);
    // for(var i=1 ; i < 5; i++){
    this.timer = setInterval(this.scrollAnimate, 3000);
    this.letTimer = setInterval(this.letAnimate, 3000);

  },
  methods: {
    go() {
      this.$router.push({ name: 'testDemo' });
    },
    back() {
      history.go(-1)
    },
    letAnimate(){
      this.sgxUp = true
      setTimeout(() => {
      console.log(this.showData[0])
       // this.listData.push(this.listData[this.value])
      this.showData.shift()
        // setTimeout("scrollAnimate()", 1000)
      this.sgxUp = false
        // console.log(this.value + "进入了")
        // this.value = this.value + 1
        // console.log(this.value)
        // i++;
       }, 3000)
    },
    scrollAnimate() {
      this.value++;
      // this.value++;
      // this.value = 0;
      // var i = 0
      // console.log("到这里")
      this.animateDown = true
      //  while(i<5){
      // console.log(i + "的值")
      // for(let value=0; value<this.listData.length; value++){
    //  while(this.value < 5){
      // for(var i= 5; i >0 ; i--){
      setTimeout(() => {
        console.log(this.listData[0])
       // this.listData.push(this.listData[this.value])
        this.listData.shift()
        // setTimeout("scrollAnimate()", 1000)
        this.animateDown= false
        // console.log(this.value + "进入了")
        // this.value = this.value + 1
        // console.log(this.value)
        // i++;
       }, 3000)
      // }
      //  }
      // setTimeout("", 1000)

      // }

    }
  },
  destroyed() {
    clearInterval(this.timer)
    clearInterval(this.letTimer)
  }
  // mounted () {
  //   this.$router.push({ name: 'testDemo' });
  // }
  // created() {
  // },
  // methods: {
  //   // 路由跳转到车辆详情页面，传入当前车的ID以及电话
  //   toDetail(item) {
  //     this.$router.push({ name: 'cardetail', params: { id: item.carId, mobile: item.mobile } });
  //   },
  //   // 方法传递
  //   phoneCall(mobile) {
  //     this.$emit('phoneCall', mobile);
  //   },
  //   getCarList_change() {
  //     this.$emit('getCarList_change');
  //   },

  // },
};
</script>
<style lang="scss">
.backFirst{
  position: fixed;
  top: 0%;
  left: 0%;
  width: 100%;
  z-index: -1;
}
.white{
  position: fixed;
  top:5.5%;
  left: 0%;
  width: 100%;
  height: 80%;
  z-index:-1;
}
.backSecond{
  position: fixed;
  bottom:0%;
  left: 0%;
  width: 100%;  
  z-index:-1;
}
.blue{
  position: fixed;
  left: 2%;
  top: 12%;
  z-index:1;
}
.pink{
  position: fixed;
  right:2%;
  top:24%
}
.handsome{
  position: fixed;
  left: 3%;
  top: 13.5%;
  z-index:2;
}
.you{
  position: fixed;
  right: 3%;
  top: 25.5%;
  z-index:2;
}
.handsomeSay{
  position: fixed;
  left: 10%;
  top: 12.5%;
  z-index:2;
}
.youSay{
  position: fixed;
  right: 10%;
  top: 24%;
  z-index:2;
}
.circle{
  position: fixed;
  left: 2%;
  bottom:2%;
  width: 60%;
  // height: 50%;
  z-index:2;
}
.homepage{
  position: fixed;
  right:2%;
  bottom:0.5%;
  z-index:2;
  width: 30%;
}

.marquee-wrap  {
  z-index:4;
   
  width: 600px;
  //width: 100%;
  height: 100px;
  // 指的是元素4个角的圆角半径都是20px。
  border-radius: 20px;
  // background: rgba($color: red, $alpha: 0.6);
  
  text-align: left; 

  //水平居中
  // margin: 0 auto;
  // 设置最左边
  left: 10%;
  top: 10%;
  //该元素的内容若超出了给定的宽度和高度属性，那么超出的部分将会被隐藏，不占位。
  overflow: hidden;
  
  //边框颜色
  border-color: black;
  
  position: fixed;

  .marquee-list {
    li {
      // left: 10%;
      //  top: 10%;
       //  position: fixed;

      // width: 100%;
      // height: 100%;

      // 一段文字范围
      width: 445px;
      height: 500px;
      
      
      // 溢出显示省略号
      //text-overflow: ellipsis;

      //overflow: hidden;
      
      // overflow: inherit;
      // 上 右 下 左  内边距
      //padding: 0 20px;
      padding: 10px 20px;
      //设置列表项目样式为不使用项目符号。
      list-style: none;
      //容器的高度，行高
      line-height: 40px;
      //居中
      // text-align: center;
      
      //文字靠左
      text-align: left;
      //自动换行
      word-wrap:break-word;
      
      /*单个字*/
      //文字颜色：黄色
      color: black;
      //文字大小
      font-size: 25px;
      //文字粗细
      font-weight: 400;
    }
  }
  .animate-up {
    transition: all 1s ease-in-out;
    //沿Y轴偏移60px
    transform: translateY(0px);
  }
}


.sgx-wrap  {
  z-index:4;
   
  width: 600px;
  //width: 100%;
  height: 100px;
  // 指的是元素4个角的圆角半径都是20px。
  border-radius: 20px;
  // background: rgba($color: red, $alpha: 0.6);
  
  text-align: left; 

  //水平居中
  // margin: 0 auto;
  // 设置最左边
  right: 8%;
  top: 22%;
  //该元素的内容若超出了给定的宽度和高度属性，那么超出的部分将会被隐藏，不占位。
  overflow: hidden;
  
  //边框颜色
  border-color: black;
  
  position: fixed;

  .sgx-list {
    li {
      // left: 10%;
      //  top: 10%;
       //  position: fixed;

      // width: 100%;
      // height: 100%;

      // 一段文字范围
      width: 445px;
      height: 500px;
      
      
      // 溢出显示省略号
      //text-overflow: ellipsis;

      //overflow: hidden;
      
      // overflow: inherit;
      // 上 右 下 左  内边距
      //padding: 0 20px;
      padding: 10px 20px;
      //设置列表项目样式为不使用项目符号。
      list-style: none;
      //容器的高度，行高
      line-height: 40px;
      //居中
      // text-align: center;
      
      //文字靠左
      text-align: left;
      //自动换行
      word-wrap:break-word;
      
      /*单个字*/
      //文字颜色：黄色
      color: black;
      //文字大小
      font-size: 25px;
      //文字粗细
      font-weight: 400;
    }
  }
  .sgx-up {
    transition: all 10s ease-in-out;
    //沿Y轴偏移60px
    transform: translateY(60px);
  }
}
</style>
