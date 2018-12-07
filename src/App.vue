<template>
  <div>
    <div>
      <h1>Participants list</h1>
      <ol> 
        <li v-for="p in participants">{{ p.Firstname }} {{ p.Lastname }}</li>
       
      </ol>
    </div>

    <h3>New participant</h3>
    <form @submit.prevent="addNewParticipant()">
      <label>Firstname</label>
      <input type="text" v-model="Firstname" >
      <label>Lastname</label>
      <input type="text" v-model="Lastname"> 
      <button>Add new participant</button>
    </form>
  </div>
</template>

<script>
  export default {
    data() {
      return {
      Firstname:'',
       Lastname:'',
        participants:[]
      
         } ;
    },
    methods: {
      addNewParticipant() {
        this.participants.push( { Firstname: this.Firstname, Lastname: this.Lastname  } );
        this.Firstname= ''
        this.Lastname = ''
      }
    }
  };
</script>
