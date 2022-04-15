<template>
  <div class="container">
    <div class="calendar-wraper">
      <div class="calendar-header">
        <div class="date-title" v-for="(item, index) in weekDay" :key="index">
          {{ item }}
        </div>
      </div>
      <div class="calendar-body">
        <div class="day-block"></div>
      </div>
    </div>
  </div>
</template>

<script lang="ts">
import { defineComponent, Ref, ref } from 'vue'
import dayjs from 'dayjs'
import en from 'dayjs/locale/en'

export default defineComponent({
  name: 'CalendarView',
  setup() {
    const weekDay: Array<string> = [
      'Monday',
      'Tuesday',
      'Wendsday',
      'ThursDay',
      'Friday',
      'Saturday',
      'Sunday'
    ]
    const thisYear = ref(dayjs().format('YYYY'))
    const thisMonth: Ref<number> = ref(+dayjs().format('M'))
    const thisDate: Ref<number> = ref(+dayjs().format('D'))
    const thisDay: Ref<number> = ref(+dayjs().format('d'))
    const allDay = (month: number) => {
      return dayjs(month).daysInMonth()
    }
    return {
      weekDay,
      thisMonth,
      thisDay,
      allDay
    }
  }
})
</script>

<style scoped></style>
