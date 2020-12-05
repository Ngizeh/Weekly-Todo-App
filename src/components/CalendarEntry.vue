<template>
    <div id="calendar-entry">
        <div class="calendar-entry-note">
            <input type="text" placeholder="New Event" v-model="inputEntity" @keyup.enter="submitEvent(inputEntity)"/>
            <p class="calendar-entry-day">Day of event: <span class="bold">{{ titleOfActive }}</span></p>
            <a class="button is-primary is-small is-outlined" @click="submitEvent(inputEntity)">Submit</a>
            <p style="color: red; font-size: 13px" v-if="error">You must type something first!</p>
        </div>
    </div>
</template>

<script>
import CalendarEvent from '@/components/CalendarEvent'
import { store } from '../store.js'
export default {
  name: 'CalendarEntry',
  components : {
     CalendarEvent
  },
  data() {
    return {
       inputEntity : '',
       error : false
    };
  },
  computed : {
    titleOfActive(){
      return store.getActiveDay().fullTitle
    }
  },
  methods : {
    submitEvent(eventDetails){
        if(eventDetails == '' ) return this.error = true;
        store.submitEvent(eventDetails);
        this.inputEntity = '';
        this.error = false
    }
  },
};
</script>

<style lang="css" scoped>
</style>
