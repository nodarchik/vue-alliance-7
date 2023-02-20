<template>
  <section>
    <header>
      <h1>Users</h1>
    </header>
    <user-data @add-user="addUser"></user-data>
    <ul>
      <active-user
        v-for="user in users"
        :key="user.id"
        :id="user.id"
        :name="user.name"
        :age="user.age"
        @delete="deleteUser"
      ></active-user>
    </ul>
  </section>
</template>

<script>
import ActiveUser from "./components/ActiveUser.vue";
export default {
  components: { ActiveUser },
  data() {
    return {
      users: [
        {
          id: "nodari",
          name: "nodar tchikadze",
          age: 25,
        },
        {
          id: "nodo",
          name: "nodo chikadze",
          age: 25,
        },
      ],
    };
  },
  methods: {
    addUser(name, age) {
      const newActiveUser = {
        id: new Date().toISOString(),
        name: name,
        age: age,
      };
      this.users.push(newActiveUser);
    },
    deleteUser(userId) {
      this.users = this.users.filter((user) => user.id !== userId);
    },
  },
};
</script>

<style>
* {
  box-sizing: border-box;
}
html {
  font-family: "Jost", sans-serif;
}
body {
  margin: 0;
}
header {
  box-shadow: 0 2px 8px rgba(0, 0, 0, 0.26);
  margin: 3rem auto;
  border-radius: 10px;
  padding: 1rem;
  background-color: #1a93f7;
  color: white;
  text-align: center;
  width: 90%;
  max-width: 40rem;
}
#app ul {
  margin: 0;
  list-style: none;
  float: left;
  width:fit-content;
  padding: 1rem;
}
#app li,
#app form{
  box-shadow: 0 2px 8px rgba(0, 0, 0, 0.26);
  margin: 1rem auto;
  border-radius: 10px;
  padding: 1rem;
  text-align: center;
  width: auto;
  max-width: 40rem;
}
#app h2 {
  font-size: 2rem;
  border-bottom: 4px solid #ccc;
  color: #58004d;
  margin: 0 0 1rem 0;
}
#app button {
  font: inherit;
  cursor: pointer;
  border: 1px solid #071520;
  background-color: #1a93f7;
  color: white;
  padding: 0.05rem 1rem;
  box-shadow: 1px 1px 2px rgba(0, 0, 0, 0.26);
}
#app button:hover,
#app button:active {
  background-color: #31ecae;
  border-color: #31ecae;
  box-shadow: 1px 1px 4px rgba(0, 0, 0, 0.26);
}
#app input {
  font: inherit;
  padding: 0.15rem;
}
#app label {
  font-weight: bold;
  margin-right: 1rem;
  width: 7rem;
  display: inline-block;
}
#app form div {
  margin: 1rem 0;
}
</style>
