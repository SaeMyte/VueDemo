<script lang="ts">
export default {
  name: "Car",

}
</script>

<!--set语法糖-->
<script lang="ts" setup>
import {reactive} from "vue";
// 数据
let car = reactive({brande: '奔驰', price: 100});
let games = reactive([
  {id: "id1", name: "王者荣耀"},
  {id: "id2", name: "三国杀"},
  {id: "id3", name: "元神"},
]);

const handleUpateGameName = (game, item) => {
  game.name = "测试" + item;
}

const handleClickPrice = () => {
  car.price += 10;
}
</script>

<template>
  <div class="person">
    <h2>一辆{{ car.brande }}车,价值{{ car.price }}万</h2>
    <button @click="handleClickPrice">修改汽车价格</button>
    <ol>
      <li v-for="(game, item) in games" key="game.id">
        {{ game.name }}
        <button @click="handleUpateGameName(game, item)">修改游戏名称</button>
      </li>
    </ol>
  </div>
</template>

<style scoped>
.person {
  background-color: skyblue;
  box-shadow: 0 0 10px;
  border-radius: 10px;
  padding: 20px;
}

button {
  margin: 0 10px;
}
</style>