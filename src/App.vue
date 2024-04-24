<template>

<div>
  <div class="black-bg" v-if="modalstate == true">
    <div class="white-bg">
      <h4>상세페이지</h4>
      <p>상세페이지 내용</p>
      <button @click="modalstate = false">X</button>
    </div>
    
  </div>
  <div class="menu">
    <!-- 자료 안의 데이터 갯수만큼 반복됨, 작명한 변수는 데이터 안의 자료가 됨 -->
    <a v-for="(menu, index) in menus" :key="index">{{ menu }}</a>
  </div>
  <h1>원룸샵</h1>
  <br />

<div style="display:flex">
  <div v-for="(product, index) in products" :key="index" class="box">
    <h4 @click="modalstate = true">{{ product }}</h4>
    <p>{{ price[index] }} 만원</p>
    <button @click="counts[index] += 1">허위매물신고</button>
    <span> 신고 수 : {{ counts[index] }}</span>
  </div>
</div>

  <hr>

<div style="display:flex">
  <div class="box">
    <img src="./assets/room0.jpg" alt="">
    <h4 @click="modalstate = true">{{ products[0] }}</h4>
    <p>{{ price[2] }} 만원</p>
    <button @click="counts[0] ++">허위매물신고</button> <span>신고 수 : {{ counts[0] }}</span>
    <p>
      버튼 설명 : click 말고도 mouseover 등등 종류가 많음.
    </p>
  </div>
  <div class="box">
    <img src="./assets/room1.jpg" alt="">
    <h4>{{ products[1] }}</h4>
    <p>{{ price[2] }} 만원</p>
    <button @click="counts[1] ++">허위매물신고</button> <span>신고 수 : {{ counts[1] }}</span>
  </div>
  <div class="box">
    <img src="./assets/room2.png" alt="">
    <h4>{{ products[2] }}</h4>
    <p>{{ price[2] }} 만원</p>
    <button @click="counts[2] ++">허위매물신고</button> <span>신고 수 : {{ counts[2] }}</span>
  </div>
  </div>
</div>

</template>

<script>

export default {
  name: 'App',
  data(){
    return {
      modalstate : false,
      counts : [ 0,0,0 ],
      price : [50, 30, 60],
      products: ['역삼동원룸', '화곡역원룸', '마포구투룸'],
      menus: ['Home', 'Shop', 'About']
    }
  },
  components: {
  },
  methods: { // vue 에서 함수만들고 싶을 때 사용
  },
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

body {
  margin: 0;
}

div {
  box-sizing: border-box;
}

.menu {
  background: darkolivegreen;
  padding: 15px;
  border-radius: 5px;
}

.menu a {
  color: white;
  padding: 10px;
}

.box {
  border: 1px solid #2c3e50;
  border-radius: 15px;
  padding: 10px;
  margin: 15px;
  width: 500px;
}

img {
  width: 100%;
  height: auto;
}

.black-bg {
  width: 100%; height: 100%;
  background: rgba(0,0,0,0.5);
  position: fixed;
  padding: 20px;
}

.white-bg {
  width: 100%; background: white;
  border-radius: 8px;
  padding: 20px;
}

</style>
