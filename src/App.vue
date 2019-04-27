<template>
  <div>
  <h2>test</h2>
  <p>{{ email }}</p>
  <input type="email" v-model="email">
  <h2>{{ email }}</h2>
  <div v-if="email.length < 10">Ale masz krótki adres!</div>
  <div v-else-if="email.length < 15">Twój adres e-mail jest w sam raz.</div>
  <div v-else>Twój adres e-mail jest stanowczo za długi.</div>
  <button @click="alertMyEmail()">Wyświetl mój e-mail w alercie</button>
  <br /><br />


  <div v-if="isHidden">
    <p>jestes zalogowany</p>
    <button @click="logMeOut()">Wyloguj</button>
  </div>
  <div v-else>
    <input type="email" v-model="email">
    <button @click="zalobujByEmail()">Zaloguj</button>
  </div>


  </div>
</template>

<script>
import HelloWorld from './components/HelloWorld.vue'

export default {
  data(){
	  return{
		  email: 'test@test.pl',
		  password: '',
      isHidden: false
	  };
  },
  methods: {
    alertMyEmail() {
        alert(this.email);
    },
    zalobujByEmail(){
        this.isHidden= true
    },
    logMeOut(){
        this.isHidden= false,
        this.email = ''
    }
  }
}
</script>

<style>

</style>
