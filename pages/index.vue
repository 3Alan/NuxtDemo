<template>
  <div class="container">
    <!-- <logo /> -->
    <nuxt-link :to="{ name: 'todo', params: { pathName: 'index'} }">
      <el-button type="primary" class="todo-btn">todoDemo</el-button>
    </nuxt-link>
    <div class="dynamic-router">
      <p>动态路由</p>
      <el-cascader :options="routeOptions" v-model="selectOption" @change="handleChange"></el-cascader>
      <el-button type="primary" @click="dynamicRoute">访问动态路由</el-button>
    </div>
  </div>
</template>

<script>
import Logo from '~/components/Logo.vue'

export default {
  components: {
    Logo
  },
  data() {
    return {
      routeOptions: [
        { value: 1, label: '路由1' },
        { value: 2, label: '路由2' },
        { value: 3, label: '路由3' }
      ],
      selectOption: '',
      ab: 13
    }
  },
  methods: {
    handleChange(value) {
      this.selectOption = value[0];
    },
    dynamicRoute() {
      console.log(this.selectOption);
    }
  }
}
</script>

<style>
.container {
  margin: 0 auto;
  min-height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;
  text-align: center;
  flex-direction: column;
}
.todo-btn {
  background: #00c58e;
  border: #00c58e;
  display: block;
  margin-bottom: 30px;
}
.dynamic-router p {
  margin-bottom: 10px;
}
</style>
