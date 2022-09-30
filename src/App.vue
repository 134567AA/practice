<template>

  <div class="menu">
    <a v-for="(yes,no) in menu" v-bind:key="no" >{{yes}}</a>

  </div>
  <!-- <div v-for="(pro,i) in product" v-bind:key="i">
    <h4>{{pro}}</h4>
    <p>{{price1[0]}} 만원</p>
  </div> -->
<div>
  <h4>{{product[0]}}</h4>
  <p>{{price1[0]}}만원 </p>
  <button @click="increase">허위 매물 신고</button> <span>신고수 : {{신고수[0]}}</span>
</div>
<div>
  <h4>{{product[1]}}</h4>
  <p>{{price1[1]}}만원 </p>
    <button @click="신고수[1]++">허위 매물 신고</button> <span>신고수 : {{신고수[1]}}</span>
</div>
<div>
  <h4>{{product[2]}}</h4>
  <p>{{price1[2]}}만원 </p>
    <button @click="신고수[2]++">허위 매물 신고</button> <span>신고수 : {{신고수[2]}}</span>
</div>

</template>

<script>

/**{{ 데이터 바인딩 }}*/
/** 데이터 변경 시 손쉽게 하기위해서
 *  실시간 자동 렌더링 쓰려면 데이터 바인딩 해야함
 *  웹앱같은거 만들기 쉬워짐 (쇼핑몰 가격필터 등등)
  */
export default {
  name: 'App',
  data() {
    return{
      신고수 : [0,0,0],
      price1 : [60,70,80],
      menu :['Home', 'Shop','About'],
      product : ['역삼동 원룸','천호동 원룸','마포구 원룸'],
    }
  },
  methods :{
    increase(){
      this.신고수[0] += 1
    }
  }
  ,
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

.menu{
  background-color: darkblue;
  padding: 15px;
  border-radius: 5px;

}
.menu a{
  text-decoration: none;
  display: inline-block;
  color: white;
  width : 150px;
}
</style>
