<template>
  <div id="app">
     <CalendarWeek/>
     <CalendarEntry/>
  </div>
</template>

<script>
import CalendarEntry from '@/components/CalendarEntry'
import CalendarWeek from '@/components/CalendarWeek'
export default {
  name: 'App',
  components : {
    CalendarWeek,
    CalendarEntry
  }
}
</script>

<style lang="scss" src="../public/styles.scss"></style>
