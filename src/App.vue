<template>
  <Calendar />
</template>
<script lang="ts">
  import { defineComponent } from "vue";
  import Calendar from "./components/Calendar.vue";

  export default defineComponent({
    name: "App",
    components: {
      Calendar,
    }
  });
</script>
<style>
@import "./assets/base.scss";
@import "./assets/calendar.scss";
</style>
