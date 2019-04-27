<template>
   <div>
       <label>Login Page</label>
       <p>jestes zalogowany {{ username }}</p>
       <!-- emituje zdarzenie logout przy kliknieciu -->
       <button @click="$emit('logout')">Wyloguj</button>
       <br/><br/>
       <p>
         Lista spotkań
       </p>
       <button @click="addNewMeeting()">Dodaj nowe spotkanie</button>
       <ol>
        <li v-for="item in meetings" :key="item.id">{{ item }}</li>
      </ol>
   </div>
</template>

<script>
export default {
  props: ['username'],
  data(){
    return{
      meetings: [
        'MWO',
        'TO',
        'INNE'
      ]
    };
  },
  methods: {
    addNewMeeting(meeting) {
      this.meetings.push('meeting');
    }
  }
}
</script>
