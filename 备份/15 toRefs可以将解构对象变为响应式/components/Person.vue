<script lang="ts">
export default {
  name: "Person",

}
</script>

<!--set语法糖-->
<script lang="ts" setup>
/**
 * 1. toRefs可以把一个reactive对象解构成一个个ref对象
 * 2. toRef一个一个取得ref响应式解构对象
 */
import {reactive, toRefs} from "vue";

let person = reactive({
  name: "张三",
  age: 18,
})

let {name, age} = toRefs(person);
let {name1} = toRefs(person, "name");
const handleClickUpdateName = () => {
  name.value = "lisi";
}
const handleClickUpdateAge = () => {
  age.value += 1;
}

</script>

<template>
  <div class="person">
    <h2>姓名:{{ name }}</h2>
    <h2>年龄:{{ age }}</h2>
    <button @click="handleClickUpdateName">修改姓名</button>
    <button @click="handleClickUpdateAge">修改年龄</button>
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