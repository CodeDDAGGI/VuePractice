<template>

  <div class="black-bg" v-if="modal === true">
    <div class="white-bg">
      <h4>상세 페이지</h4>
      <p>상세 페이지 내용</p>
    <button @click="modal=false">닫기</button>
    </div>
  </div>

  <div class="menu">
    <a v-for="(a,i) in highbar" :key="i">{{i}} {{ a }}</a>
  </div>
  
  <div>
    <img :src="oneroom[0].image" class="room-img">
    <h4>{{oneroom[0].title}}</h4>
    <p>{{oneroom[0].price}}</p>
    <p>{{oneroom[0].content}}</p>
  </div>

  <div v-for="(room,index) in oneroom" :key="index">
    <img :src="room.image" class="room-img">
    <h4>{{room.title}}</h4>
    <p>가격 : {{room.price}} 원</p>
    <p>내용 : {{room.content}}</p>
  </div>
  
  <!-- <div v-for="a in products" :key="a">
    <h4 v-for="(a,i) in products" :key="i">{{a}} 상품{{i + 1}}
    </h4>
      <p v-for="a in price" :key="a">가격 : {{a}} 만원</p>
    <button v-for="a in count" :key="a" @click="increase">{{text}}</button>
  </div> -->
  <!-- <div>
    <img src="./assets/room0.jpg" class="room-img">
    <h4 @click ="modal = true">{{products[0]}}상품1</h4>
    <p>가격 : {{price[0]}} 만원</p>
    <button @click="count[0]++">허위매물신고</button>
    <span>신고수 : {{count[0]}}</span>
  </div>
  <div>
    <img src="./assets/room1.jpg" class="room-img">
    <h4 @click ="modal = true">{{products[1]}}상품2</h4>
    <p>가격 : {{price[1]}} 만원</p>
    <button @click="count[1]++">허위매물신고</button>
    <span>신고수 : {{count[1]}}</span>
  </div>
  <div>
    <img src="./assets/room2.jpg" class="room-img">
    <h4 @click ="modal = true">{{products[2]}}상품2</h4>
    <p>가격 : {{price[2]}} 만원</p>
    <button @click="count[2]++">허위매물신고</button>
    <span>신고수 : {{count[2]}}</span>
  </div> -->
</template>

<script>
import data from './assets/oneroom.js';

export default {
  name: 'App',
  data() {
    return {
      // 오브젝트 자료형으로 값을 넣음
      modal: false,
      count : [0,0,0],
      products : ['역삼동','천호동', '마포구'],
      price : [70,40, 30],
      highbar : ["Home" , "Shop", "About"],
      text:"허위매물신고",
      oneroom :data
    }
  },
  methods : {
    increase(){
      this.count += 1;
    },
    decrease(){
      this.count -= 1;
    },
  },
  components: {
    
  }
}
</script>

<style>
body{
  margin: 0;
}
div{
  box-sizing: border-box;
}
.black-bg{
  width: 100%;
  height: 100%;
  background: rgba(0,0,0,0.5);
  position: fixed;
  padding: 20px;
}
.white-bg{
  width: 100%;
  background: white;
  border-radius: 8px;
  padding: 20px;
}
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

.menu {
  background: darkslateblue;
  padding: 15px;
  border-radius: 5px;
}

.menu a {
  color: white;
  padding: 10px;
}

.room-img {
  width: 100%;
  margin-top: 40px;

}
</style>
