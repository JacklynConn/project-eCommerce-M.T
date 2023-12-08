<template>
  <div>
    <form @submit.prevent="handleSubmit">
      <h3>Signup Form</h3>
      <label for="">Username</label>
      <input type="text" v-model="username" />
      <label for="">Email</label>
      <input type="email" v-model="email" />
      <label for="">Password</label>
      <input type="password" v-model="password" />
      <label for="">Role</label>
      <select v-model="role">
        <option value="programmer">Programmer</option>
        <option value="developer">Developer</option>
        <option value="designer">Designer</option>
      </select>
      <label for="">Skill</label>
      <input type="text" v-model="skill" @keypress.space="handleAddSkill" />
      <span>{{ skills }}</span>
      <div>
        <input type="checkbox" v-model="terms" />
        <label for="">AGREE TERMS AND CONDITION</label>
      </div>
      <button>Submit</button>
    </form>
    <p>Username: {{ username }}</p>
    <p>Email: {{ email }}</p>
    <p>Password: {{ password }}</p>
    <p>Role: {{ role }}</p>
    <p>Skill: {{ skillS }}</p>
    <p>Terms: {{ terms }}</p>
  </div>
</template>

<script>
import { ref } from "vue";
export default {
  setup() {
    const username = ref("");
    const email = ref("");
    const password = ref("");
    const role = ref("");
    const skill = ref("");
    const skills = ref([]);
    const terms = ref(false);

    const handleAddSkill = (e) => {
      skills.value.push(skill.value);
      skill.value = "";
    };

    const handleSubmit = (e) => {
      e.preventDefault();
      console.log(`
        Username: ${username.value}
        Email: ${email.value}
        Password: ${password.value}
        Role: ${role.value}
        Skill: ${skills.value}
        Agree Terms: ${terms.value ? "Yes" : "No"}}`
        );
    };

    return {
      username,
      email,
      password,
      role,
      skill,
      skills,
      terms,
      handleAddSkill,
      handleSubmit,
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
input, select {
  display: block;
  color: #aaa;
  padding: 10px 6px;
  width: 100%;
  border: none;
  border-bottom: 1px solid #ddd;
  font-size: 25px;
}
span{
  margin: 10px 0;
  font-size: 30px;
  color: blue;
}
input[type="checkbox"]{
  display: inline-block;
  margin: 0 20px 0 0;
  width: 20px;

}
button{
  display: block;
  margin: 20px 0 0;
  padding: 10px 20px;
  background-color: blue;
  color: white;
  font-size: 25px;
  border: none;
  border-radius: 5px;
}

</style>
