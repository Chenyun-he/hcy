<template>
 <!--这个是第二个  -->

  <div class=""> 
    哈嗲省地矿局哈萨克好打算
     <div class="footer">
            <input id="text" type="text" v-model.trim="inputValue" @keyup.enter='chat' placeholder="说点什么吧...">
            <!-- <span id="btn" @click="btn2()">发送</span> -->
    </div>
    <ul class="content" ref="charView">
            <li v-for="(item, index) in messageList" :key="index">
                <!-- <span img :src="handsome" class="fuck" style="z-index:5;width:25px;height:25px;" > </span> -->
                <span :class="'span'+(item.myself?'right':'left')">{{item.message}}</span>
                <!-- <span img :src="you" class="letgo" style="z-index:5;width:25px;height:25px;"></span> -->

            </li>
    </ul>
  
  <img :src="backFirst" class="backFirst">
  <img :src="white" class="white">
  <img :src="backSecond" class="backSecond">
  <img :src="blue" class="blue">
  <img :src="pink" class="pink">
  <img :src="handsome" class="handsome">
  <img :src="you" class="you">
  <!-- <img :src="handsomeSay" class="handsomeSay"> -->
  <!-- <img :src="youSay" class="youSay"> -->
  <img :src="circle" class="circle">
  <img :src="homepage" class="homepage" @click="comBack">
  </div>
</template>



<script>
import $ from 'jquery'
var content  = $(".content")
import backFirstDefault from '@/assets/picture/second/backFirst.png'
import whiteDefault from '@/assets/picture/second/white.png'
import backSecondDefault from '@/assets/picture/second/backSecond.png'
import blueDefault from '@/assets/picture/second/blue.png'
import pinkDefault from '@/assets/picture/second/pink.png'
import handsomeDefault from '@/assets/picture/second/handsome.png'
import youDefault from '@/assets/picture/second/you.png'
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
      circle:circleDefault,
      homepage:homepageDefault,
      animateUp: false,
      sgxUp:false,
      inputValue: '',
      count:0,
      messageList: ['你好啊','哈哈哈','你是什么东西'],
      ReplayList: ['M吗（心中窃喜）FWB懂吗？',
'我想给你买件衣服不知道是什么码数 请问是S吗',
'那你喜欢什么颜色的麻袋？',
 '你每天都会照镜子吧 真羡慕你 每天都能见到我喜欢的人',
'其实我是NTR爱好者，你了解吗',
'或者来我家 尝尝我做的饭啊', 
'你喜欢什么制服 被我制服可以吗',
'说实话我想要两个女儿，你呢',
 '哦对了，多了一张电影票 晚上一起看吗 不然浪费了',
 '结尾:月吗？857吗？'
]

    };
  },
  mounted() {
    this.box=this.$refs.charView;
  },
  methods: {
              comBack(){
                  this.$router.push('/');
              },
              chat() {
                var _this=this;
                // console.log(_this.$refs.charView);
                this.messageList.push({
                    message: this.inputValue,
                    //这个是判断当前是否是自己输入的内容,自己的是true,机器人的是false
                    myself: true
                })
                 console.log(1);
                // console.log(message)
                // console.log(this.inputValue);
                //每次发送信息之后机器人就要回复,所以添加完之后直接调用机器人的接口
                // $.ajax({
                //     url: 'http://www.tuling123.com/openapi/api',
                //     type: 'post',
                //     data: {
                //         key: 'e5e78db64c3744fda06533e6729737da',
                //         info: this.inputValue,
                //         box:""
                //     },
                //     success: (data) => {
                //         // console.log(data);
                //         this.messageList.push({
                //             message: data.text,
                //             myself: false
                            
                //         });
                //         _this.$refs.charView.scrollTop+=999;
                //     }
                // })
                  this.messageList.push({
                    message:  this.ReplayList[this.count],
                    myself: false  
                });
                _this.$refs.charView.scrollTop+=999;
                this.count++;
                this.inputValue=""
            },
            btn1(){
                this.$router.go(-1)
            },
            // btn2(){        
            //     this.messageList.push({
            //         message: this.inputValue,
            //         //这个是判断当前是否是自己输入的内容,自己的是true,机器人的是false
            //         myself: true
            //     })
            //     // console.log(1);
            //     // console.log(message)
            //     // console.log(this.inputValue);
            //     //每次发送信息之后机器人就要回复,所以添加完之后直接调用机器人的接口
            //     $.ajax({
            //         url: 'http://www.tuling123.com/openapi/api',
            //         type: 'post',
            //         data: {
            //             key: 'e5e78db64c3744fda06533e6729737da',
            //             info: this.inputValue
            //         },
            //         success: (data) => {
            //             // console.log(data);
            //             this.messageList.push({
            //                 message: data.text,
            //                 myself: false
            //             });
                        
            //         }
            //     })                             
            //     this.inputValue=""
            // },
           

    go() {
      this.$router.push({ name: 'testDemo' });
    },
    back() {
      history.go(-1)
    },
  }
};
</script>
<style lang="scss">
.backFirst{
  position: fixed;
  top: 0%;
  left: 0%;
  width: 100%;
  z-index: 10;
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
// .handsomeSay{
//   position: fixed;
//   left: 10%;
//   top: 12.5%;
//   z-index:2;
// }
// .youSay{
//   position: fixed;
//   right: 10%;
//   top: 24%;
//   z-index:2;
// }
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

// .marquee-wrap  {
//   z-index:4;
   
//   width: 600px;
//   //width: 100%;
//   height: 100px;
//   // 指的是元素4个角的圆角半径都是20px。
//   border-radius: 20px;
//   // background: rgba($color: red, $alpha: 0.6);
  
//   text-align: left; 

//   //水平居中
//   // margin: 0 auto;
//   // 设置最左边
//   left: 10%;
//   top: 10%;
//   //该元素的内容若超出了给定的宽度和高度属性，那么超出的部分将会被隐藏，不占位。
//   overflow: hidden;
  
//   //边框颜色
//   border-color: black;
  
//   position: fixed;

//   .marquee-list {
//     li {
//       // left: 10%;
//       //  top: 10%;
//        //  position: fixed;

//       // width: 100%;
//       // height: 100%;

//       // 一段文字范围
//       width: 445px;
//       height: 500px;
      
      
//       // 溢出显示省略号
//       //text-overflow: ellipsis;

//       //overflow: hidden;
      
//       // overflow: inherit;
//       // 上 右 下 左  内边距
//       //padding: 0 20px;
//       padding: 10px 20px;
//       //设置列表项目样式为不使用项目符号。
//       list-style: none;
//       //容器的高度，行高
//       line-height: 40px;
//       //居中
//       // text-align: center;
      
//       //文字靠左
//       text-align: left;
//       //自动换行
//       word-wrap:break-word;
      
//       /*单个字*/
//       //文字颜色：黄色
//       color: black;
//       //文字大小
//       font-size: 25px;
//       //文字粗细
//       font-weight: 400;
//     }
//   }
//   .animate-up {
//     transition: all 1s ease-in-out;
//     //沿Y轴偏移60px
//     transform: translateY(0px);
//   }
// }


// .sgx-wrap  {
//   z-index:4;
   
//   width: 600px;
//   //width: 100%;
//   height: 100px;
//   // 指的是元素4个角的圆角半径都是20px。
//   border-radius: 20px;
//   // background: rgba($color: red, $alpha: 0.6);
  
//   text-align: left; 

//   //水平居中
//   // margin: 0 auto;
//   // 设置最左边
//   right: 8%;
//   top: 22%;
//   //该元素的内容若超出了给定的宽度和高度属性，那么超出的部分将会被隐藏，不占位。
//   overflow: hidden;
  
//   //边框颜色
//   border-color: black;
  
//   position: fixed;

//   .sgx-list {
//     li {
//       // left: 10%;
//       //  top: 10%;
//        //  position: fixed;

//       // width: 100%;
//       // height: 100%;

//       // 一段文字范围
//       width: 445px;
//       height: 500px;
      
      
//       // 溢出显示省略号
//       //text-overflow: ellipsis;

//       //overflow: hidden;
      
//       // overflow: inherit;
//       // 上 右 下 左  内边距
//       //padding: 0 20px;
//       padding: 10px 20px;
//       //设置列表项目样式为不使用项目符号。
//       list-style: none;
//       //容器的高度，行高
//       line-height: 40px;
//       //居中
//       // text-align: center;
      
//       //文字靠左
//       text-align: left;
//       //自动换行
//       word-wrap:break-word;
      
//       /*单个字*/
//       //文字颜色：黄色
//       color: black;
//       //文字大小
//       font-size: 25px;
//       //文字粗细
//       font-weight: 400;
//     }
//   }
  // .sgx-up {
  //   transition: all 10s ease-in-out;
  //   //沿Y轴偏移60px
  //   transform: translateY(60px);
  // }
// }


.footer {
        z-index:5;
        // 
        // width: 100vw;
        // width: 500px;
        // height: 70px;
        // background:white;
        // rgba(102, 102, 102, 0);
        // position: fixed;
        // bottom: 0;
        // overflow: hidden;
        // left: 0%;
        // right: 30%;
    }
    .footer input {
            z-index:5;
            bottom: 3.5%;
            // margin-top: 10px;
            left: 4%;
            // width: 70vw;
            width: 55%;
            height: 50px;
            outline: none;
            font-size: 20px;
            text-indent: 10px;
            position: fixed;
            border-radius: 6px;
            // margin-left: 10px;
        }
        
        .footer span {
            z-index:5;
            // margin-top: 10px;
            display: inline-block;
            // width: 20vw;
            width: 100px;
            left: 53%;
            bottom: 3.7%;
            height: 48px;
            background: #ccc;
            font-weight: 900;
            line-height: 45px;
            cursor: pointer;
            text-align: center;
            position: fixed;
            // right: 10px;
            border-radius: 6px;
        }
        .footer span:hover {
            z-index:1;
            color: #fff;
            background: #999;
        }
        
         .content {
            // background: #fff;
            top: -5%;
            z-index:10;
            right: 15%;
            left: 7%;
            font-size: 20px;
            // left: 50%;
            //width: 100vw;
            width: 80%;
            height: 675px;
            overflow: auto;
            position: absolute;
          
        }
        .content li {
            z-index:1;
            margin-top: 5px;
            display: block;
            clear: both;
            overflow: hidden;
        }
        .content li img {
            float: left;
        }
        .content li span{
            background: #7cfc00;
            padding: 10px;
            border-radius: 10px;
            float: left;
            margin: 6px 10px 0 10px;
            max-width: 310px;
            border: 1px solid #ccc;
            box-shadow: 0 0 3px #ccc;
            word-break: break-all 
        }
        
        .content li span.spanleft {  
            z-index:8;
            float: left;
            background: 00BBFF;
        }
        .content li span.spanright { 
            z-index:8;
            float: right;
            background: pink;
        } 

</style>
