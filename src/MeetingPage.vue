<template>
    <div>
       <h2>Zajęcia</h2>
       <new-meeting-form 
       @added="addNewMeeting($event)">
       </new-meeting-form>
       
       <meetings-list 
       :meetings="meetings"
       :user="user"
       @subscribe="addParticipant($event)"
       @removed="removeMeeting($event)">>
       </meetings-list>
    </div>
</template>

<script>
import NewMeetingForm from "./NewMeetingForm";
import MeetingsList from "./MeetingsList";

export default {
  components: {NewMeetingForm, MeetingsList},
  props: ['user'],
  data() {
      return {
          meetings: []
      };
  },
  methods: {
      addNewMeeting(meeting) {
          this.meetings.push(meeting);
      },
      removeMeeting(meeting) {
        this.meetings = this.meetings.filter((event) => {
          return event !== meeting;
        });
      },
      addParticipant(meeting) {
        meeting.participants.push(this.user);
      },
  }
}
</script>