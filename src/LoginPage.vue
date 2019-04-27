<template>
   <div>
       <label>Login Page</label>
       <p>jestes zalogowany {{ username }}</p>
       <!-- emituje zdarzenie logout przy kliknieciu -->
       <button @click="$emit('logout')">Wyloguj</button>
   </div>
</template>

<script>
export default {
  props: ['username'],
}
</script>
