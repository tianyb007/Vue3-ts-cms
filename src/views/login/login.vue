<template>
  <div class="login">
    <login-panel />
    <el-icon :size="50" color="red">
      <Edit />
    </el-icon>
  </div>
</template>

<script setup lang="ts">
console.log('-----------')
import LoginPanel from './c-cpns/login-panel.vue'
</script>

<style lang="less" scoped>
.login {
  display: flex;
  align-items: center;
  justify-content: center;
  width: 100%;
  height: 100%;
  background-image: url(../../assets/img/login-bg.svg);
}
</style>
