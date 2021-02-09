<template>
  <div class="app">
    <h1 v-x="2">{{ total }}</h1>
    <Child v-y :high.sync="total"></Child>
    <form @submit="onsubmit()">
      <label>
        <span>用户名：</span>
        <input type="text" v-model="user.userName">
      </label>
      <label>
        <span>密码：</span>
        <input type="password" v-model="user.password">
      </label>
      <button type="submit">登录</button>
    </form>
    <label>
      <span>Jack</span>
      <input type="checkbox" :value="1" v-model="array">
    </label>
    <label>
      <span>Rose</span>
      <input type="checkbox" :value="2" v-model="array">
    </label>
    <label>
      <span>Jim</span>
      <input type="checkbox" :value="3" v-model="array">
    </label>
    <div>{{array}}</div>

    <MyInput :b="value" @c="a"></MyInput>
    <div>{{value}}111</div>

    <br>
    <br>
    <br>
    <br>
    <br>
    <div>
      <antdDemo></antdDemo>
    </div>
  </div>
</template>

<script>
import Child from "./components/Child";
import MyInput from "./components/MyInput";
import antdDemo from "./components/antdDemo";


export default {
  data() {
    return {
      total: 1,
      user: {
        userName: '',
        password: '',
      },
      value:undefined,
      array:[]
    }
  },
  methods: {
    onsubmit() {
      console.log(this.user.userName);
    },
    a($event){
      this.value = $event.target.value
    }
  },
  components: {
    Child,
    MyInput,
    antdDemo
  },
  directives: {
    y: {
      inserted(el) {
        el.addEventListener('click', () => {
        })
        console.log('y');
      }
    }
  }
}
</script>

<style scoped>
.app {
  border: 1px solid #ff0000;
}
</style>