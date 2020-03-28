<template>
    <div id="calendar-week" class="container">
      <div class="columns is-mobile">
        <CalendarDay v-for="(day, index) in sharedState.seedData" :day="day" :key="index"/>
      </div>
    </div>
</template>

<script>
import { store } from '../store.js'
import CalendarDay from '@/components/CalendarDay';
export default {
  name: 'CalendarWeek',
  components : {
    CalendarDay
  },
  data() {
    return {
      sharedState : store.state
    };
  },
};
</script>

<style lang="css" scoped>
</style>
