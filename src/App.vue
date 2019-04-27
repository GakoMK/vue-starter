<template>
  <div>
  <!-- <h2>test</h2>
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
    <form @submit.prevents="">
      <input type="email" v-model="email">
      <button @click="zalobujByEmail()">Zaloguj</button>
    </form>
  </div> -->
  <h2></h2>
  <div v-if="email.length > 0">
    <!-- <p>jestes zalogowany {{ email }}</p>
    <button @click="logMeOut()">Wyloguj</button> -->
    <login-page :username="email" @logout="logMeOut()"></login-page>
  </div>
  <div v-else>

    <!-- <login-form @login="logMeIn($event)"></login-form> -->

    <login-form @login="logMeIn($event)" :button-label="'Wejdź'" header="Rejestracja"></login-form>
     <!-- bez : to bedzie string -> :button-label -->
    <login-form @login="logMeIn($event)" :button-label="'Wejdź'" header="Rejestracja"></login-form>
    <login-form @login="logMeIn($event)" :button-label="'Wleć'" header="Rejestracja 2"></login-form>
    <login-form @login="logMeIn($event)" :button-label="'Zaloguj się jak człowiek'" header="Rejestracja 3"></login-form>
  </div>


  </div>
</template>

<script>

import LoginForm from "./LoginForm";
import LoginPage from "./LoginPage";
import "milligram";

export default {
  components: {LoginForm, LoginPage},
  data(){
	  return{
		  email: '',
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
    // logMeOut(){
    //     this.isHidden= false,
    //     this.email = ''
    // },
    logMeIn(username) {
      this.email = username;
    },
    logMeOut(){
      this.email = '';
    }
  }
}
</script>

<style>

</style>
