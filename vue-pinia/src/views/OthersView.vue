<script setup>
import { storeToRefs } from 'pinia'
import { useOtherStore } from '../stores/other'

const { datas } = storeToRefs(useOtherStore())
const { fetchOthers } = useOtherStore()

fetchOthers()
</script>

<template>
  <div>
    <p v-if="datas" v-for="data in datas" :key="data.id">
      {{ data.name }}
    </p>
  </div>
</template>