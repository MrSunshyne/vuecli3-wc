<template>
  <div>
      <h1>Hello {{name}}</h1>
      <input type="text" v-model="name">
      <div :key="item.id" v-for="item in message">
        <img :src="item.avatar" alt="">
        {{ item.first_name}}
      </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      name: "Sandeep",
      image: "",
      message: ""
    };
  },
  mounted() {
    fetch("https://reqres.in/api/users?page=2")
      .then(response => {
        return response.json();
      })
      .then(myJson => {
        this.message = myJson.data;
      });
  }
};
</script>
