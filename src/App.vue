<script setup>
import {NForm,NFormItem,NInputNumber} from 'naive-ui'
import {ref} from "vue";

const form = ref({
  area: undefined,
  number: undefined
})
const formRef = ref()
const rules = {
  area: { required: true, trigger: ['blur', 'input'], message: '请输入总面积', type: 'number' },
  number: { required: true, trigger: ['blur', 'input'], message: '请输入总人数', type: 'number' },
}
</script>

<template>
  <div class="box">
    <n-form ref="formRef" :model="form" :rules="rules">
      <n-form-item label="Area" path="area">
        <n-input-number v-model:value="form.area" :max="999999" />
      </n-form-item>
      <n-form-item label="Number" path="number">
        <n-input-number v-model:value="form.number" :max="999999.99" :precision="2" />
      </n-form-item>
    </n-form>
  </div>
</template>
<style scoped>
.box {
  height: 100%;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
}
</style>
