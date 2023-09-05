<template>

  <div class="nav">
    <a href="" v-for="(data, i) in nav" :key="i">{{data}}</a>
    <!-- nav array의 자료 개수만큼 for in 반복문을 돌려줌~! -->
    <!-- <태그 v-for="작명 in 몇회" :key="작명" > key 꼭 써줘야 에러 안남-->
    <!-- key의 용도는? 반복문 돌린 요소를 컴퓨터가 구분하기 위해 씀 i 는 index 비슷하게 사용 됨: 0 1 2 -->
  </div>
  
  <div class="black-bg" v-if="(modal == true)">
  <div class="white-bg">
    <h4>상세페이지임</h4>
    <p>상세페이지 내용임</p>
    <button @click="modal = false">창 닫기</button>
  </div>
</div>

  <!-- 반복문 돌리기 -->
  <h1>팅커벨의 방 구하기</h1>
  <div v-for="(area, i) in areas" :key="i">
    <img @click="modal = true" src= "./assets/room0.jpg" alt="원룸방" class="photo">
    <h4>{{area}}</h4>
    <p>전세 {{prices[i]}}만원</p> 
    <button @click="신고수[i]++">허위매물신고</button> <span>신고수 : <em>{{신고수[i]}}</em></span>
  </div>

<!-- v-on:click="자바스크립트(코드가 길어지면 아래 함수로 만들어서 사용하기)" -->
<!-- @click @mouseover @input 기타 등등 이벤트 명이 있음 -->

</template>

<script>


export default {
  name: 'App',
  // 데이터 바인딩 
  // 데이터 바인딩 하는 이유? 하드 코딩하면 변경이 어려워서 + 실시간 자동 랜더링 이용 (web-app가능), 자주 바뀌는것을 사용 

  // data 보관함, 변수 이곳에 저장함 : object 형식으로 저장 
  // 사용시 {{데이터 이름}} 해서 데이터 바인딩 하면 됨 

  // HTML 속성도 데이터 바인딩 가능! :속성 = "데이터이름"

  data(){
    return{
      modal : false,
      prices : [4500, 7000, 10000],
      스타일 : 'color : orange',
      nav : ['Home', 'Products', 'About'],
      areas : ['신갈동 원룸', '수지구청 원룸', '미금역 오피스텔'],
      신고수 : [0,0,0],
    }
  },
  methods : {
    // increase() {
    // 사용시에는 increase 만 쓰면 됨 
    // this.신고수 += 1;
    // }
  },

  components: {
  }
}
</script>

<style lang="scss">
// @import "@/asstes/scss/파일명";
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

body {
  margin : 0;
}
div {
  box-sizing: border-box;
}

.nav {
  background: rgb(139, 61, 108);
  padding: 15px;
  border-radius: 5px;
}

.nav a {
  color: white;
  padding: 20px;
  text-decoration: none;
  font-weight: 700;
  font-size: 1.2rem;
  letter-spacing: 1px;
}

.photo {
  width: 60%;
  margin-top: 40px;
  cursor: pointer;
}

button {
  cursor: pointer;
  border-radius: 5px;
}

// 모달창 : html, css 먼저 만들기 
// 동적이 UI 만들기 
// 1. UI 현재 상태를 데이터로 저장하기 
// 2. 데이터에 따라 UI가 어떻게 보일지 작성 

.black-bg {
  width: 100%; 
  height:100%;
  background: rgba(0,0,0,0.5);
  position: fixed; padding: 20px;
}
.white-bg {
  width: 100%; background: pink;
  border-radius: 8px;
  padding: 20px;
} 

</style>
