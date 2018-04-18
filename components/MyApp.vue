<template>
  <div class="app-container" :class="themeName">
      <h1>Hello {{name}}</h1>
      <input type="text" v-model="name">
      <div :key="item.id" v-for="item in message">
        <img :src="item.avatar" alt="">
        {{ item.first_name}}
      </div>

      <p><strong>{{ themeName }}</strong></p>
  </div>
</template>

<script>
export default {
  props: ["theme"],
  data() {
    return {
      name: "Sandeep",
      image: "",
      message: ""
    };
  },
  computed: {
    themeName() {
      return typeof this.theme === "undefined"
        ? "No theme specified"
        : this.theme;
    }
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

<style lang="scss" scoped>
.app-container {
  background: gray;

  &.amigo {
    background: blue;
  }
}
</style>
