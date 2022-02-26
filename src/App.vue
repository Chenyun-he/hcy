<template>
  <div class="start">
    <!-- <div style="width:100%;height:100%;position: relative"> -->
    <!-- <img :src="backgroundImg"> -->
    <!-- <img :src="background1Img" class="background1Img"> -->
    
    <!-- 
    <div>
    <img :src="defaultImg" class="defaultImg">
    <img :src="pickImg" class="pickImg">
    </div> 
    -->
    <!-- <div class="wenzi">
    密好
    </div> -->
    <div class="defaultImg changePic" style="background:black">
    <img src="./assets/picture/first/pick.png">
    </div>
    
    <div class="pickImg changePic1">
    <img src="./assets/picture/first/pick.png">
    </div>

    <div class="loveImg changePic2">
    <img src="./assets/picture/first/love.png">
    </div>

    <div class="love1Img changePic3">   
    <img src="./assets/picture/first/love1.png" > 
    <!-- <img :src="love1Img" > -->
    </div>
   
    <div class="lockImg">
    <img src="./assets/picture/first/lock2.png">  
    </div>
    
    <div class="lock1Img">
    <img src="./assets/picture/first/lock1.png">  
    </div>
    
    <div class="lock2Img">
    <img src="./assets/picture/first/lock.png">  
    </div>
    
    <div class="sloganImg changePic4" >
    <img src="./assets/picture/first/slogan.png"  @click="dragDemo" />
    </div>
    
    <div class="slogan1Img changePic5">
    <img src="./assets/picture/first/slogan1.png"  @click="vueSlicksortPractice" />
    </div>

    <div class="slogan2Img changePic6">
    <img src="./assets/picture/first/slogan2.png"  @click="canBack" />
    </div>

    <!-- <img :src="slogan1Img" class="slogan1Img" @click="vueSlicksortPractice" />
    <img :src="slogan2Img" class="slogan2Img" @click="canBack" /> -->

    <!-- <img :src="lock1Img" class="lock1Img"> 
    <img :src="lock2Img" class="lock2Img"> -->
    
    <!-- <img :src="sloganImg" class="sloganImg" @click="dragDemo" />
    <img :src="slogan1Img" class="slogan1Img" @click="vueSlicksortPractice" />
    <img :src="slogan2Img" class="slogan2Img" @click="canBack" /> -->

    <!-- <img :src="lockImg" class="lockImg">  
    <img :src="lock1Img" class="lock1Img"> 
    <img :src="lock2Img" class="lock2Img">
    
    <img :src="sloganImg" class="sloganImg" @click="dragDemo" />
    <img :src="slogan1Img" class="slogan1Img" @click="vueSlicksortPractice" />
    <img :src="slogan2Img" class="slogan2Img" @click="canBack" /> -->

    <!-- <router-link to="/dragDemo">dragDemo第一个</router-link>
    <span style = 'margin-left: 200px;'></span>
    <router-link to="/vueSlicksortPractice">vueSlicksortPractice第二个</router-link>
    <span style = 'margin-left: 200px;'></span>
    <router-link to="/canBack">canBack第三个</router-link> -->
    
    <!-- <router-view></router-view> -->
    <!-- <HelloWorld/> -->
  </div> 
</template>

<script>
// import HelloWorld from './components/HelloWorld'
// import deImgDefault from '@/assets/picture/first/track02.png'
// import pickImgDefault from '@/assets/picture/first/pick.png'
// import loveImgDefault from '@/assets/picture/first/love.png'
// import love1ImgDefault from '@/assets/picture/first/love1.png'
import lockImgDefault from '@/assets/picture/first/lock.png'
import lock1ImgDefault from '@/assets/picture/first/lock1.png'
import lock2ImgDefault from '@/assets/picture/first/lock2.png'
import sloganImgDefault from '@/assets/picture/first/slogan.png'
import slogan1ImgDefault from '@/assets/picture/first/slogan1.png'
import slogan2ImgDefault from '@/assets/picture/first/slogan2.png'
// import backgroundImgDefault from '@/assets/picture/first/background.png'
// import background1ImgDefault from '@/assets/picture/first/background1.png'
// import testDefault from '@/assets/picture/first/test.png'
export default {
  name: 'App',
  data () {
    return {
      // backgroundImg:backgroundImgDefault,
      // background1Img:background1ImgDefault,
      // defaultImg:deImgDefault,
      // pickImg:pickImgDefault,
      // loveImg:loveImgDefault, //loveImgDefault,
      love1Img:love1ImgDefault,
      lockImg:lockImgDefault,
      lock1Img:lock1ImgDefault,
      lock2Img:lock2ImgDefault,
      sloganImg:sloganImgDefault,
      slogan1Img:slogan1ImgDefault,
      slogan2Img:slogan2ImgDefault,
      // testImg:testDefault
    }
  },
  methods:{
   dragDemo(){
   this.$router.push('dragDemo');
   },
   vueSlicksortPractice(){
   this.$router.push('vueSlicksortPractice');
   },
   canBack(){
   this.$router.push('canBack');
   }
  //   changeActive($event){
  //   $event.currentTarget.className="things active";
  //   // loveTest = testDefault;
  // },
  //   changeActive(){
  //    loveTest = loveImgDefault;
  // },
  //   removeActive(){
  //   loveTest = testDefault;
  // }
  }

 

  // watch: {
  //   list1: {
  //     handler: function (newVal, oldVal) {
  //       console.log('bbbbbb')
  //     },
  //     deep: true
  //   }
  // },
  // components: {
  //   HelloWorld
  // }
}
</script>

<style>
    /* .defaultImg{ */
      /* background-position:90% -200%; */
      /* background:url(./assets/picture/first/background1.png) center center / cover no-repeat; */
      /* background-size:150%; */
      /* 向上移动一点 */

      /* right: 50%; */
      /* margin-top: -2%; */
      /* 缩小0.6倍 */
      /* transform: scale(0.5);  */
      /* transform:scale(0.6); */
      /* 图片水平居中 */
      /* position: relative; */
      /* display: fixed;  */
      /* justify-content: center;  */
      /* 背景：黑色 */
      /* background: black; */

      /* background-position: center 0; */


      /* border: 50px; */
      /* background-position:center; */
    /* } */
    .pickImg{
      margin-top: -3%;
      /* 缩小0.6倍 */
      transform: scale(0.75); 
      /* 图片水平居中 */
      display: flex; 
      justify-content: center; 
      /* 背景：黑色 */
      /* background: black; */
      /* display:flex; */
      /* position: fixed;
      margin:0 auto;
      margin-top:1%; */
      /* background: black; */
      /* width:3%; */ 
    }
    /* .loveImg:hover img{
      content:url(@/assets/picture/first/lock1.png);
    } */
    .loveImg{
      position: fixed;
      left: 2%;
      top: 25%;  
    }
     /* .wenzi{
      position: fixed;
      left: 2%;
      top: 25%;  
    } */
    /* .testImg{
      position: fixed;
      left: 5%;
      top: 30%;  
    } */
    .love1Img{
      position:fixed;
      right: 2%;
      top: 25%;
    }
    .lockImg{
      position: fixed;
      left:40%;
      top:35%;
    }
    .lock1Img{
      position: fixed;
      left:60%;
      top:35%;
    }
    .lock2Img{
      position:fixed;
      left:20%;
      top:35%;
    }
    .sloganImg {
      position:fixed;
      left:20%;
      top:70%;
    }
    .slogan1Img{
      position: fixed;
      left:40%;
      top:70%;
    }
    .slogan2Img{
      position: fixed;
      left:60%;
      top:70%;
    }
    /* .changePic:hover img {
    content: url(./assets/picture/first/track999.png);
    } */
    .changePic1:hover img {
    content: url(./assets/picture/first/pick02.png);
    }
    .changePic2:hover img {
    content: url(./assets/picture/first/yello.png);
    }
    .changePic3:hover img {
    content: url(./assets/picture/first/yello2.png);
    }
    .changePic4:hover img {
      transform: scale(1.2);
    }
    .changePic5:hover img {
      transform: scale(1.2);
    }
    .changePic6:hover img {
      transform: scale(1.2);
    }

   

    
  /* a{
    text-decoration: none;
  }
  *{
    margin: 0;
    padding: 0;
  }
  ul, li {
    list-style: none;
  } */
  /*#app {
    font-family: 'Avenir', Helvetica, Arial, sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    text-align: center;
    color: #2c3e50;
    margin-top: 60px;
  }*/
  /* .ctn{
    line-height: 50px;
    cursor: pointer;
    font-size: 20px;
    text-align: center;
    float: left;
  }
  .sub:hover{
      background: #e6dcdc;
      color: white;
      width: 100px;
  } */
  /* .ctn1{
    border: 1px solid green;
    width: 100px;
  }
  .ctn2{
    border: 1px solid black;
    width: 100px;
    margin-left: 50px;
  }
  .dragCtn{
    width: 100px;
  }
  .fixed{
    position: fixed;
    background: red;
    cursor: move;
    pointer-events: none;
  } */
  /* .fixedCtnBorder{
    border: 1px solid red;
    border-style: dashed;
    width: 100px;
    height: 50px;
  } */


/* body {
  background: #FAFAFF;
  padding: 20px;
  font-family: Helvetica;
} */

/*#app {
  background: #EEE;
  border-radius: 4px;
  border: 1px solid #EEE;
  transition: all 0.2s;
}*/

/* li {
  padding: 20px;
  list-style-type: none;
  cursor: pointer;
  background: #FFF;
  border-bottom: 1px solid #EEE;
  -webkit-user-select: none;
  -moz-user-select: none;
  -ms-user-select: none;
  user-select: none;
}

h2 {
  font-weight: bold;
  margin-bottom: 15px;
} */

</style>
