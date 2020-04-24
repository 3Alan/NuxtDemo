<template>
  <el-alert :title="`我是从路由${1}过来的`" type="success"></el-alert>
</template>

<script>
export default {
  validate({ params }) {
    return /^\d+$/.test(params.route);
  }
}
</script>

<style>
</style>