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
</div>


</template>

<script>

export default {
  name: 'App',
  data(){
    return {
      price : [50, 30, 60],
      products: ['역삼동원룸', '화곡역원룸', '마포구투룸'],
      menus: ['Home', 'Shop', 'About']
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

.menu {
  background: darkolivegreen;
  padding: 15px;
  border-radius: 5px;
}

.menu a {
  color: white;
  padding: 10px;
}
</style>
