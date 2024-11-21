<template>
<div id="schedule"></div>
  <v-container>
    <h2 class="text-center">Event Schedule</h2>
    <v-row>
      <v-col  v-for="event in events" :key="event.id">
        <v-card class="schedule-card">
            <img src="../assets/rose-removebg-preview.png" alt="rose">
          <v-card-title>{{ event.title }}</v-card-title>
          <v-card-subtitle>{{ event.date }}</v-card-subtitle>
          <v-card-subtitle>{{ event.time }}</v-card-subtitle>
          <v-card-text>
            <p>{{ event.venue }}</p>
          </v-card-text>
           <v-card-actions>
            <v-menu
              v-model="event.menu"
              offset-y
              bottom
              transition="scale-transition"
            >
              <template #activator="{ props }">
                <v-btn v-bind="props" color="success" class="schedule-btn">
                  Save the Date
                </v-btn>
              </template>

              <v-list>
                <v-list-item
                  v-for="calendar in event.calendars"
                  :key="calendar.name"
                  @click="saveToCalendar(calendar.url)"
                >
                  <v-list-item-title>{{ calendar.name }}</v-list-item-title>
                </v-list-item>
              </v-list>
            </v-menu>
          </v-card-actions>
        </v-card>
      </v-col>
    </v-row>
  </v-container>
</template>


<script>
export default {
  data() {
    return {
      events: [
        {
          id: 1,
          title: "Traditional Wedding",
          date: "Sat, August 16, 2025",
          time: "8:00 AM",
          venue: "Jogor Center, Liberty Ring Road Ibadan",
          calendars: [
            {
              name: "Google Calendar",
              url: "https://calendar.google.com/calendar/r/eventedit?dates=20240601T180000Z/20240601T220000Z&details=Reception&location=Reception+Venue",
            },
            {
              name: "Apple Calendar",
              url: "webdata:text/calendar;charset=utf8,BEGIN:VCALENDAR%0AVERSION:2.0%0ABEGIN:VEVENT%0AURL:https://thebtaffairs-2024.inawo.wedding/%0ADTSTART:20241123T120000Z%0ADTEND:20241124T120000Z%0ASUMMARY:Reception%0ADESCRIPTION:null%0ALOCATION:Comfort%20Akinfenwa%20Hall,%20Opp%20St%20Annes,%20Molete,%20Ibadan%0AEND:VEVENT%0AEND:VCALENDAR",
            },
            {
              name: "Yahoo",
              url: "https://calendar.yahoo.com/?v=60&view=d&type=20&title=Reception&st=20241123T120000Z&dur=2400&in_loc=Comfort%20Akinfenwa%20Hall%2C%20Opp%20St%20Annes%2C%20Molete%2C%20Ibadan",
            },
            {
              name: "Outlook",
              url: "data:text/calendar;charset=utf8,BEGIN:VCALENDAR%0AVERSION:2.0%0ABEGIN:VEVENT%0AURL:https://thebtaffairs-2024.inawo.wedding/%0ADTSTART:20241123T120000Z%0ADTEND:20241124T120000Z%0ASUMMARY:Reception%0ADESCRIPTION:null%0ALOCATION:Comfort%20Akinfenwa%20Hall,%20Opp%20St%20Annes,%20Molete,%20Ibadan%0AEND:VEVENT%0AEND:VCALENDAR",
            },
          ],
        },
        {
          id: 2,
          title: "Church Service",
          date: "Saturday, August 16, 2024",
          time: "11:00 AM",
          venue: "Global Harvest Church Outer Ring Road Ibadan",
          calendars: [
            {
              name: "Google Calendar",
              url: "https://calendar.google.com/calendar/r/eventedit?dates=20240601T140000Z/20240601T160000Z&details=Church+Service&location=Church+Venue",
            },
            {
              name: "Apple Calendar",
              url: "data:text/calendar;charset=utf8,BEGIN:VCALENDAR%0AVERSION:2.0%0ABEGIN:VEVENT%0AURL:https://thebtaffairs-2024.inawo.wedding/%0ADTSTART:20241123T120000Z%0ADTEND:20241124T120000Z%0ASUMMARY:Reception%0ADESCRIPTION:null%0ALOCATION:Comfort%20Akinfenwa%20Hall,%20Opp%20St%20Annes,%20Molete,%20Ibadan%0AEND:VEVENT%0AEND:VCALENDAR",
            },
             {
              name: "Yahoo",
              url: "https://calendar.yahoo.com/?v=60&view=d&type=20&title=Reception&st=20241123T120000Z&dur=2400&in_loc=Comfort%20Akinfenwa%20Hall%2C%20Opp%20St%20Annes%2C%20Molete%2C%20Ibadan",
            },
            {
              name: "Outlook",
              url: "data:text/calendar;charset=utf8,BEGIN:VCALENDAR%0AVERSION:2.0%0ABEGIN:VEVENT%0AURL:https://thebtaffairs-2024.inawo.wedding/%0ADTSTART:20241123T120000Z%0ADTEND:20241124T120000Z%0ASUMMARY:Reception%0ADESCRIPTION:null%0ALOCATION:Comfort%20Akinfenwa%20Hall,%20Opp%20St%20Annes,%20Molete,%20Ibadan%0AEND:VEVENT%0AEND:VCALENDAR",
            },
          ],
        },
           {
          id: 3,
          title: "Reception",
          date: "Saturday, August 16, 2024",
          time: "2:00 PM",
          venue: "Jogor Center, Liberty Ring Road Ibadan",
          calendars: [
            {
              name: "Google Calendar",
              url: "https://calendar.google.com/calendar/r/eventedit?dates=20240601T140000Z/20240601T160000Z&details=Church+Service&location=Church+Venue",
            },
            {
              name: "Apple Calendar",
              url: "data:text/calendar;charset=utf8,BEGIN:VCALENDAR%0AVERSION:2.0%0ABEGIN:VEVENT%0AURL:https://thebtaffairs-2024.inawo.wedding/%0ADTSTART:20241123T120000Z%0ADTEND:20241124T120000Z%0ASUMMARY:Reception%0ADESCRIPTION:null%0ALOCATION:Comfort%20Akinfenwa%20Hall,%20Opp%20St%20Annes,%20Molete,%20Ibadan%0AEND:VEVENT%0AEND:VCALENDAR",
            },
             {
              name: "Yahoo",
              url: "https://calendar.yahoo.com/?v=60&view=d&type=20&title=Reception&st=20241123T120000Z&dur=2400&in_loc=Comfort%20Akinfenwa%20Hall%2C%20Opp%20St%20Annes%2C%20Molete%2C%20Ibadan",
            },
            {
              name: "Outlook",
              url: "data:text/calendar;charset=utf8,BEGIN:VCALENDAR%0AVERSION:2.0%0ABEGIN:VEVENT%0AURL:https://thebtaffairs-2024.inawo.wedding/%0ADTSTART:20241123T120000Z%0ADTEND:20241124T120000Z%0ASUMMARY:Reception%0ADESCRIPTION:null%0ALOCATION:Comfort%20Akinfenwa%20Hall,%20Opp%20St%20Annes,%20Molete,%20Ibadan%0AEND:VEVENT%0AEND:VCALENDAR",
            },
          ],
        },
           {
          id: 4,
          title: "After-Party",
          date: "Saturday, August 16, 2024",
          time: "6:00 PM",
          venue: "Jogor Center, Liberty Ring Road Ibadan",
          calendars: [
            {
              name: "Google Calendar",
              url: "https://calendar.google.com/calendar/r/eventedit?dates=20240601T140000Z/20240601T160000Z&details=Church+Service&location=Church+Venue",
            },
            {
              name: "Apple Calendar",
              url: "data:text/calendar;charset=utf8,BEGIN:VCALENDAR%0AVERSION:2.0%0ABEGIN:VEVENT%0AURL:https://thebtaffairs-2024.inawo.wedding/%0ADTSTART:20241123T120000Z%0ADTEND:20241124T120000Z%0ASUMMARY:Reception%0ADESCRIPTION:null%0ALOCATION:Comfort%20Akinfenwa%20Hall,%20Opp%20St%20Annes,%20Molete,%20Ibadan%0AEND:VEVENT%0AEND:VCALENDAR",
            },
             {
              name: "Yahoo",
              url: "https://calendar.yahoo.com/?v=60&view=d&type=20&title=Reception&st=20241123T120000Z&dur=2400&in_loc=Comfort%20Akinfenwa%20Hall%2C%20Opp%20St%20Annes%2C%20Molete%2C%20Ibadan",
            },
            {
              name: "Outlook",
              url: "data:text/calendar;charset=utf8,BEGIN:VCALENDAR%0AVERSION:2.0%0ABEGIN:VEVENT%0AURL:https://thebtaffairs-2024.inawo.wedding/%0ADTSTART:20241123T120000Z%0ADTEND:20241124T120000Z%0ASUMMARY:Reception%0ADESCRIPTION:null%0ALOCATION:Comfort%20Akinfenwa%20Hall,%20Opp%20St%20Annes,%20Molete,%20Ibadan%0AEND:VEVENT%0AEND:VCALENDAR",
            },
          ],
        },
        
      ],
      
    };
  },
  methods: {
    saveToCalendar(url) {
      window.open(url, "_blank");
    },
  },
};
</script>


<style scoped>
.text-center {
    text-align: center;
    margin-bottom: 20px;
}
.schedule-card{
    text-align: center;
}
.schedule-btn{
    margin: auto;
    background-color: black;
}
</style>