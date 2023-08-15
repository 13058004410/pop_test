<script setup>
import { ref, onMounted, reactive } from 'vue'
import mack from 'C:/Users/admin/Desktop/mock/mock.json'


defineProps({
  msg: String,
})

const count = ref(0)
const open = ref(false)
const arr = reactive([])
const showModal = values =>{
  open.value = true
  console.log('弹窗提示',values)
}
const handleOk = values =>{
  open.value = false;
  console.log('关闭窗口',values)
}
onMounted(()=>{
  arr.value = mack.data.records
  console.log('组件挂载完毕',arr)
})
</script>

<template>
 <div>
    <a-button type="primary" @click="showModal">点击弹窗</a-button>
    <a-modal v-model:open="open" title="提示" @ok="handleOk" ok-text="确定" cancel-text="取消" class="pop_up">
      <div style="height:100px;">
        <p>11111</p>
        <p>22222</p>
        <p>33333</p>
        <p>55555</p>
        <p>55555</p>
        <p>66666</p>
        <p>77777</p>
        <p>99999</p>
      </div>
    </a-modal>
  </div>
</template>

<style scoped>
.read-the-docs {
  color: #888;
}
/* .pop_up {
  float:right;
} */

.ant-modal-body p {
  float:right;
  margin-right:20px;
  width:50px !important;
}

</style>
