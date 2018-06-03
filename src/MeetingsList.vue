<template>
    <table v-if="meetings.length > 0">
        <thead>
            <tr>
                <th>Nazwa spotkania</th>
                <th>Opis</th>
                <th>Uczestnicy</th>
            </tr>
        </thead>
        <tbody>
            <tr v-for="meeting in meetings" :key="meeting.name">
                <td>{{ meeting.name }}</td>
                <td>{{ meeting.description }}</td>
                <td>
                    <ul v-if="meeting.participants.length > 0">
                        <li v-for="(participant, index) in meeting.participants" :key="index">{{ participant }}</li>
                    </ul>
                </td>
                <td>
                    <div class="float-right">
                        <button v-if="meeting.participants.indexOf(user) < 0" class="button button-outline" @click="subscribe(meeting)">Zapisz się</button>
                        <button @click="removeMeeting(meeting)">Usuń spotkanie</button>
                    </div>
                </td>
            </tr>
        </tbody>
    </table>
</template>

<script>
export default {
  props: ['meetings', 'user'],
  methods: {
      subscribe(meeting) {
        this.$emit('subscribe', meeting);
      },
      removeMeeting(meeting) {
          this.$emit("removed", meeting);
    }
  }
};
</script>