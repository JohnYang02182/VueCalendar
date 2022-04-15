<template>
  <div class="container">
    <div class="calendar-wraper">
      <div class="calendar-header">
        <div class="date-title" v-for="(item, index) in weekDay" :key="index">
          {{ item }}
        </div>
      </div>
      <div class="calendar-body"></div>
    </div>
  </div>
</template>

<style scoped>
</style>

<script lang="ts">
import { defineComponent, ref } from 'vue'
import * as dayjs from 'dayjs'
import en from 'dayjs/locale/en'

export default defineComponent({
  name: 'Calendar',
  setup() {
    const weekDay: Array<string> = ['Monday','Tuesday','Wendsday','ThursDay','Friday','Saturday','Sunday'],
    const now = ref(dayjs())
    return {
      weekDay,
      now
    }
  },
})
</script>

