<template>
  <div>
    <el-tag type="danger">
      <i class="el-icon-warning"></i>
      {{error.statusCode}}
    </el-tag>
    <el-alert :title="error.message" type="error"></el-alert>
    <ul>
      <li>
        <nuxt-link to="/">HOME</nuxt-link>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  props: ['error'],
  created() {
    console.log(this.error)
  }
}
</script>