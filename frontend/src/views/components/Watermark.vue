<template>
  <el-switch v-model="wmBollean" @change="wmChange" size="large" inline-prompt style="--el-switch-off-color: #9999999e" active-text="移除水印" inactive-text="官方水印" />
</template>

<script setup lang="ts">
import { ref } from 'vue'
import { useBaseStore } from '@/store'

const baseStore = useBaseStore()
const wmBollean = ref(false)

function wmChange(isRemove: string | number | boolean) {
  baseStore.changeWatermark(isRemove ? '' : ['DOMIAI.NET'])
}
</script>
