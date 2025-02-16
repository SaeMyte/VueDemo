<script lang="ts">
export default {
  name: "Person",
  data() {
    return {
      name: "张三 ",
      age: 18,
      tel: "1388888888"
    }
  },
  methods: {
    showTel() {
      alert(this.tel)
    },
    changeName() {
      this.name = "李四"
    },
    changeAge() {
      this.age += 1;
    }
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