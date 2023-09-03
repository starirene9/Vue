<template>
  <!-- template 안에 HTML -->

  <div class="nav">
    <a href="" v-for="(data, i) in nav" :key="i">{{data}}</a>
    <!-- nav array의 자료 개수만큼 for in 반복문을 돌려줌~! -->
    <!-- <태그 v-for="작명 in 몇회" :key="작명" > key 꼭 써줘야 에러 안남-->
    <!-- key의 용도는? 반복문 돌린 요소를 컴퓨터가 구분하기 위해 씀 i 는 index 비슷하게 사용 됨: 0 1 2 -->
  </div>
  <!-- 반복문 돌리기 -->
  <h1>원룸샵</h1>
  <div v-for="(area, i) in areas" :key="i">
    <h4>{{area}}</h4>
    <p>전세 {{prices[i]}}만원</p>
  </div>
  <!-- <div>
    <h1>원룸샵</h1>
    <h4 :style="스타일">{{areas[0]}}</h4>
    <p>전세 {{price1}}만원</p>
  </div>
  <div>
    <h4>{{areas[1]}}</h4>
    <p>전세 {{price2}}만원</p>
  </div>
  <div>
    <h4>{{areas[2]}}</h4>
    <p>전세 {{price3}}만원</p>
  </div> -->
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
      prices : [4500, 7000, 10000],
      스타일 : 'color : orange',
      nav : ['Home', 'Products', 'About'],
      areas : ['구갈동 원룸', '신갈동 원룸', '동천동 오피스텔'],
    }
  },
  components: {
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

.nav {
  background: darkslateblue;
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
</style>
