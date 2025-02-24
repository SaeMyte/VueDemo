<script lang="ts">
export default {
  name: "Person",
  /**
   * 1. data，method和setup可以同时存在
   * 2. setup比data执行的早，所以在data中可以读取到setup中的数据;反过来不能
   * 3. setup里面没有this
   */
  data() {
    return {
      a: 100,
      name: this.name,
    }
  },
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
    <h2>{{ a }}</h2>
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