<template>
  <form v-on:submit.prevent="submitForm">
    <div>
      <label for="username">id: </label>
      <!-- v-model : two-way binding -->
      <input id="username" type="text" v-model="username">
    </div>

    <div>
      <label for="password">pw: </label>
      <input id="password" type="password" v-model="password">
    </div>
    <button type="submit">login</button>
  </form>
</template>

<script>
import axios from 'axios';

export default {
  data: function() {
    return {
      username: '',
      password: ''
    }
  },
  methods: {
    submitForm: function(event) {
      event.preventDefault();

      var url = 'https://jsonplaceholder.typicode.com/users';
      var data = {
        username: this.username,
        password: this.password
      }

      axios.post(url, data)
      .then(function(response) {  // 성공 시
        console.log(response)
      })
      .catch(function(error) { // 실패 시
        console.log(error)
      });
      console.log(this.username, this.password);
    }
  }
}
</script>

<style>

</style>