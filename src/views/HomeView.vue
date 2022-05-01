<template>
  <div class="home">
     <header>
      <div class="header">
        <div class="title"><h1>水果商城</h1></div>
        <div class="search">
          <input type="text" placeholder="请输入您想搜索的商品">
          <button>搜索</button>
        </div>
      </div>
    </header>
    <div class="content">
      <!-- 热门商品 -->
      <div class="hotShopping">
        <h1>热门商品</h1>
        <ul class="hot1">
          <li v-for="item in shoppings1" :key="item.id">
            <a href="#">
              <img :src="item.src" alt="图片出错">
              <h2>{{item.title}}</h2>
              <p class="color-grey">时间：{{item.time}}</p>
              <span class="color-red border-color-red span1" >新</span>
            </a>
          </li>
        </ul>
        <ul class="hot2">
          <li v-for="item in shoppings2" :key="item.id">
             <a href="#">
              <img :src='item.src' alt="图片出错">
              <h2>{{item.title}}</h2>
              <p class="color-grey">时间：{{item.time}}</p>
            </a>
          </li>
        </ul>
      </div>
      <h2 style="text-align:start;">水果类</h2>
      <!-- 水果类商品 -->
      <div class="fruits">
        <ul>
          <li v-for="item in fruits" :key="item.id">
            <a href="#">
                <img :src="item.src" alt="">
                <!-- 注意文本溢出 -->
                <h2>{{item.title}}</h2>
                <p>时间：{{item.time}}</p>
            </a>
          </li>
        </ul>
      </div>
    </div>
  </div>
</template>

<script>
// @ is an alias to /src
// import HelloWorld from '@/components/HelloWorld.vue'

export default {
  name: 'HomeView',
  data(){
    return {
      shoppings1:[],
       shoppings2:[],
       fruits:[],
       arrs:[
         {id:1,name:'haha',title:'衣服',text:'哈哈',src:require('../assets/images/1.jpeg'),time:20200106},
        {id:2,name:'haha',title:'衣服',text:'哈哈',src:require('../assets/images/1.jpeg'),time:20200206},
        {id:3,name:'haha',title:'衣服',text:'哈哈',src:require('../assets/images/1.jpeg'),time:20200306},
        {id:4,name:'haha',title:'衣服',text:'哈哈',src:require('../assets/images/1.jpeg'),time:20200406},
        {id:5,name:'haha',title:'衣服',text:'哈哈',src:require('../assets/images/1.jpeg'),time:20200206},
        {id:6,name:'haha',title:'衣服',text:'哈哈',src:require('../assets/images/1.jpeg'),time:20200906},
        {id:7,name:'haha',title:'衣服',text:'哈哈',src:require('../assets/images/1.jpeg'),time:20200806},
        {id:8,name:'haha',title:'衣服',text:'哈哈',src:require('../assets/images/1.jpeg'),time:20210706},
        {id:9,name:'haha',title:'衣服',text:'哈哈',src:require('../assets/images/1.jpeg'),time:20210606},
        {id:10,name:'haha',title:'衣服',text:'哈哈',src:require('../assets/images/1.jpeg'),time:20210506},
        {id:11,name:'haha',title:'衣服',text:'哈哈',src:require('../assets/images/1.jpeg'),time:20210306},
        {id:12,name:'haha',title:'衣服',text:'哈哈',src:require('../assets/images/1.jpeg'),time:20210406},
        {id:13,name:'haha',title:'衣服',text:'哈哈',src:require('../assets/images/1.jpeg'),time:20220406},
        {id:14,name:'haha',title:'衣服',text:'哈哈',src:require('../assets/images/1.jpeg'),time:20220306},
      ]
    }
  },
  
 created(){
 
  //  按照最新时间来排序数组
  this.arrs.sort(function(a,b){
    return b.time-a.time
  })
//  选取相应的数组元素
this.shoppings1 = this.arrs.slice(0,2);
this.shoppings2 = this.arrs.slice(2,5);
this.fruits = this.arrs.slice(0,7);


 },
  components: {
    
  },
  methods:{

  }
}
</script>
<style>
*{
  margin: 0;
  padding: 0;
}

 .color-grey{
    color: rgb(201, 201, 201);
  }
.color-red{
  color: red;
}
.span1{
  position: absolute;
  left: 10px;
  top: 90px;
}
.border-color-red{
  border: 1px solid red;
}
 header{
   width: 100%;
   height: 100px;
   background-color: cornsilk;
 }
 .header{
   width: 1126px;
   height: 100px;
   margin: 0 auto;
   display: flex;
   justify-content: space-evenly;
   align-items: center;
 }
 .content{
   width: 1126px;
   margin: 0 auto;
 }
 .hotShopping,.fruits{
   width: 100%;
   margin: 10px;
   /* margin-top: 10px; */
 }
  .hotShopping h1{
    color: red;
    margin: 10px 0px;
  }
  .hot1,.hot2{
    width: 100%;
    height: 300px;
    display: flex;
    justify-content: space-between;
  }
  .hot1 li a,.hot2 li a{
    text-decoration: none;
    display: block;
    position: relative;
    width: 100%;
    height: 100%;
    color: black;
    /* text-align: center; */
  }
  .hot1>li{
    width: 50%;
    height: 100%;
    border: 1px solid grey;
    list-style: none;
  }
   .hot2>li{
    width: 25%;
    height: 100%;
    border: 1px solid grey;
    list-style: none;
  }
  .hot1 li a img{
    width: 50%;
    position: absolute;
    right: 0;
    top: 50%;
    transform: translateY(-50%);
 
    /* height: 100%; */
  }
  .hot1 li a h2,.hot1 li a p{
    text-align: start;
    padding-top: 10px;
    padding-left: 10px;
  }
 
 .hot2 li a img{
    width: 100%;
    position: absolute;
    bottom: 0;
    left: 0;
    right: 0;
    margin: auto;
  }
  .hot2 li a h2,.hot2 li a p{
    padding: 10px auto;
  }
 .fruits li{
   width: 100%;
   height: 100px;
   border-top: 1px solid rgb(212, 211, 211);
   border-bottom: 1px solid rgb(212, 211, 211);
 
   list-style: none;
 }
 .fruits li a{
   text-decoration: none;
   display: block;
   width: 100%;
   height: 100%;
   color: black;
     position: relative;
   /* line-height: 100px; */
 }
 .fruits li a img{
   width: 15%;
  position: absolute;
  left: 10px;
 top: 0;
 margin: 0;
 bottom: 0;
 }
 .fruits li a h2,.fruits li a p{
    padding-top: 20px;
 }
</style>