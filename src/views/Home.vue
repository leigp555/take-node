<template>
  <div class="wrap">
    <div class="form">
      <van-image
        class="img"
        round
        width="5rem"
        height="5rem"
        fit="cover"
        position="center"
        src="https://cdn.jsdelivr.net/npm/@vant/assets/cat.jpeg"
      />
      <van-form @failed="onFailed">
        <van-cell-group inset>
          <!-- 通过 pattern 进行正则校验 -->
          <van-field
            v-model="value1"
            name="pattern"
            placeholder="用户名"
            :rules="[{ pattern, message: '请输入正确内容' }]"
          />
          <van-field
            v-model="value1"
            name="pattern"
            placeholder="密码"
            :rules="[{ pattern, message: '请输入正确内容' }]"
          />
        </van-cell-group>
        <div style="margin: 16px">
          <van-button round block type="primary" native-type="submit">
            提交
          </van-button>
        </div>
      </van-form>
    </div>
  </div>
</template>

<script lang="ts" setup>
import { ref } from 'vue'

const value1 = ref('')
const pattern = /\d{6}/
const onFailed = (errorInfo) => {
  console.log('failed', errorInfo)
}
</script>

<style scoped lang="scss">
.wrap {
  background-color: #fcfafa;
  width: 100vw;
  height: 100vh;
  .form {
    width: 100%;
    position: absolute;
    top: 40%;
    left: 50%;
    transform: translate(-50%, -50%);
    > .img {
      margin-left: 50%;
      transform: translateX(-50%);
      margin-bottom: 50px;
    }
  }
}
</style>
