<template>
  <div>
    <form>
      <h3>Signup Form</h3>
      <label for="">Username</label>
      <input type="text" v-model="username" />
      <label for="">Email</label>
      <input type="email" v-model="email" />
      <label for="">Password</label>
      <input type="password" v-model="password" />
    </form>
    <p>Username: {{ username }}</p>
    <p>Email: {{ email }}</p>
    <p>Password: {{ password }}</p>
  </div>
</template>

<script>
import { ref } from "vue";
export default {
  setup() {
    const username = ref("");
    const email = ref("");
    const password = ref("");

    return {
      username,
      email,
      password,
    };
  },
};
</script>

<style>
div {
  width: 900px;
  margin: 30px auto;
}
p {
  font-size: 30px;
  color: gray;
  font-style: italic;
}
form {
  max-width: 600px;
  background-color: white;
  padding: 40px;
  border-radius: 10px;
  text-align: left;
}
h3 {
  font-size: 40px;
  color: blue;
  text-align: center;
}
label {
  display: inline-block;
  color: #aaa;
  font-size: 20px;
  margin: 25px 0 15px;
  letter-spacing: 1px;
  text-transform: uppercase;
}
input {
  display: block;
  color: #aaa;
  padding: 10px 6px;
  width: 100%;
  border: none;
  border-bottom: 1px solid #ddd;
}
</style>
