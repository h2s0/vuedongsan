<template>

<div>
  <div class="menu">
    <!-- 자료 안의 데이터 갯수만큼 반복됨, 작명한 변수는 데이터 안의 자료가 됨 -->
    <a v-for="(menu, index) in menus" :key="index">{{ menu }}</a>
  </div>
  <h1>원룸샵</h1>
  <br />

  <div v-for="(product, index) in products" :key="index">
    <h4>{{ product }}</h4>
    <p>{{ price[index] }} 만원</p>
  </div>

  <hr>

<div style="display:flex">
  <div class="box">
    <h4>{{ products[0] }}</h4>
    <p>{{ price[2] }} 만원</p>
    <button @click="counts">허위매물신고</button> <span>신고 수 : {{ count }}</span>
    <p>
      버튼 설명 : click 말고도 mouseover 등등 종류가 많음.
    </p>
  </div>
  <div class="box">
    <h4>{{ products[1] }}</h4>
    <p>{{ price[2] }} 만원</p>
    <button @click="counts1">허위매물신고</button> <span>신고 수 : {{ count1 }}</span>
  </div>
  <div class="box">
    <h4>{{ products[2] }}</h4>
    <p>{{ price[2] }} 만원</p>
    <button @click="counts2">허위매물신고</button> <span>신고 수 : {{ count2 }}</span>
  </div>
  </div>
</div>

</template>

<script>

export default {
  name: 'App',
  data(){
    return {
      count : 0,
      count1 : 0,
      count2 : 0,
      price : [50, 30, 60],
      products: ['역삼동원룸', '화곡역원룸', '마포구투룸'],
      menus: ['Home', 'Shop', 'About']
    }
  },
  components: {
  },
  methods: { // vue 에서 함수만들고 싶을 때 사용
    counts() {
      this.count += 1;
    },
    counts1() {
      this.count1 += 1;
    },
    counts2() {
      this.count2 += 1;
    },
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
</style>
