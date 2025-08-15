<script>
import { CalendarView, CalendarViewHeader } from "vue-simple-calendar"
import "../../node_modules/vue-simple-calendar/dist/css/default.css";
import "../../node_modules/vue-simple-calendar/dist/vue-simple-calendar.css";
import "../../node_modules/vue-simple-calendar/dist/css/holidays-us.css";

export default {
		name: 'app',
		data: function() {
			return {
        showDate: new Date(),
        currentPeriodLabel: "Today",
        startingDayOfWeek: 0,
        monthNameFormat: "long",
        items: [{
          id: "1",
          startDate: new Date(Date.now()), // Make this change after midnight
          endDate: new Date(Date.now()), // Make this change after midnight
          title: "You are here."
        },
        {
            id: "2",
            startDate: new Date("October 29, 2025"),
            endDate: new Date("October 29, 2025"), 
            title: "Title"
        }
        ]
       }
		},
		components: {
            CalendarView,
			CalendarViewHeader,
		},
		methods: {
			setShowDate(d) {
        console.log(d);
				this.showDate = d;
			},
		}
	}
</script>
<template>
    <div id="app">
      <CalendarView
      :show-date="showDate"
      :starting-day-of-week="startingDayOfWeek"
      :month-name-format="monthNameFormat" 
      :items="items"
    >
      <template #header="{ headerProps }">
        <CalendarViewHeader :header-props @input="setShowDate"/>
      </template>
    </CalendarView>
    </div>
  </template>
  
  <style scoped>
    .calendar-wrapper{
        display: flex;
        flex-direction: column;
        flex-grow: 1;
        font-family: 'Avenir', Helvetica, Arial, sans-serif;
        color: #2c3e50;
        height: 67vh;
        width: 90vw;
        margin-left: auto;
        margin-right: auto;
    }
  </style>