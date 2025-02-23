<script lang="ts">
export default {
  name: "Person",
  // setup执行时机比beforeCreate还早
  setup() {
    let name = "zhangsan";
    let age = 18;
    let tel = "13888888888";

    // 方法
    function showTel() {
      alert(tel);
    }

    function changeName() {
      name = "zhangsan";
    }

    function changeAge() {
      age += 1;
    }

    return {name, age, changeAge, showTel, changeName};
  }
}
</script>

<template>
  <div class="person">
    <h2>姓名:{{ name }}</h2>
    <h2>年龄:{{ age }}</h2>
    <button @click="changeName">修改姓名</button>
    <button @click="changeAge">修改年龄</button>
    <button @click="showTel">查看联系方式</button>
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