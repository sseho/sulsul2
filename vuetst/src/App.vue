<template>

  <div class="black-bg" v-if="모달창열림 == true"> 
    <div class="white-bg">
      <h4>구독목록</h4>
      <div v-for="(a,i) in 원룸들" :key="i">
        <div v-if="구독수[i] == 'o' ">
          <h5>{{원룸들[i].name}} </h5>
        </div>
      </div>
      <button @click="모달창열림 = false">닫기</button>
    </div>
  </div>

<div>
  <h1>더 주 (The 酒)</h1>
</div>
  <div class="menu">
    <a v-for="(a,i) in 메뉴들" :key="i"> {{a}} </a>
  </div>
  <hr>
  
  <div v-for="(a,i) in 원룸들" :key="i" class="jul" >
    <img :src="원룸들[i].image" class="room-img"> <br>
    <h4>술 : {{원룸들[i].name}}</h4>
    <h4>회사명 :{{원룸들[i].company}}</h4>
    <h4>{{원룸들[i].type}}</h4>
    <h4>도수 : {{원룸들[i].density}}도</h4>
    <!-- <input type="checkbox" >{{원룸들[i].title}} <br> -->
    <!-- <h4 @click="모달창열림 = true" class="sul">{{원룸들[i].title}} </h4> -->
    <h4>{{원룸들[i].price}}원 </h4>
    <!-- <span>체크한 이름: {{ checkedNames }}</span> -->
    <button @click="구독수[i]='o' ">선택</button> <button @click="구독수[i]='x' ">취소</button> <span>구독 : {{구독수[i]}} </span>
    <hr>
  </div>

  <div>
    <h4 @click="모달창열림 = true" class="sul"> -- 구독하기 -- </h4>
  </div>


<br>
</template>

<script>

import data from './assets/data.js';



export default {
  name: 'App',
  data(){
    return {
      원룸들 : data,
      모달창열림 : false,
      메뉴들 : ['Home', 'Shop', 'About','Login'],
      products : ['역삼동원룸', '천호동원룸', '마포구원룸'],
      구독수 : ['x','x','x','x','x','x','x','x','x','x','x','x','x','x','x','x','x','x','x','x','x','x','x','x'],
    }
  },
  methods : {

  },
  components: {
  }
}
</script>




<style>
body {
  margin: 0
}
div {
  box-sizing: border-box;
}
.black-bg {
  width: 100%; height: 100%;
  background: rgba(0, 0, 0, 0.5);
  position: fixed; padding: 20px;
}
.white-bg {
  width: 100%; 
  background: white;
  border-radius: 8px;
  padding: 20px;
}
.sul {
  width: 100%;
}
.room-img {
  width: 20%;
  margin-top: 10px;
}
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 30px;
}

.menu {
  background: skyblue;
  padding: 15px;
  border-radius: 5px;
}
.menu a {
  color: white;
  padding: 10px;
}
.jul h4 {
  line-height: 10%;
  /* padding: 0px; */
}
</style>
