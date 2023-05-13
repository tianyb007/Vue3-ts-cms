<template>
  <div class="pane-account">
    <el-form label-width="60px" size="large" :model="account" :rules="accountRules" status-icon>
      <el-form-item label="账号" prop="name">
        <el-input v-model="account.name" />
      </el-form-item>
      <el-form-item label="密码" prop="password">
        <el-input v-model="account.password" show-password />
      </el-form-item>
    </el-form>
  </div>
</template>

<script setup lang="ts">
import { reactive } from 'vue'
import type { FormRules } from 'element-plus'
// 1、定义account数据
const account = reactive({
  name: '',
  password: ''
})

// 2、定义校验规则
const accountRules: FormRules = {
  name: [
    { required: true, message: 'Please input Activity name', trigger: 'blur' },
    { min: 3, max: 10, message: 'Length should be 3 to 10', trigger: 'blur' }
  ],
  password: [
    { required: true, message: 'Please input password', trigger: 'blur' },
    { pattern: /^[a-z0-9]{3,}$/, message: '最低3位以上数字和字母组成', trigger: 'blur' }
  ]
}

// 3、定义登录规则
function loginAction() {
  console.log('function excution')
}
defineExpose({ loginAction })
</script>

<style lang="less" scoped>
.pane-account {
  color: red;
}
</style>
