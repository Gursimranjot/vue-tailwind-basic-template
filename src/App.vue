<template>
  <div id="app" class="container mx-auto">
    <div id="nav">
      <router-link to="/">Home</router-link> |
      <router-link to="/about">About</router-link> |
      <!-- <router-link to="/users">users</router-link> -->
      <router-link :to="{ name: 'users' }">Users</router-link> |

      <router-link :to="{ name: 'usersProfile' }">profile</router-link>
      <!-- <router-link :to="{ name: 'usersProfile' }">profile</router-link> -->
      <!-- usersProfile -->
    </div>
    <router-view />
  </div>
</template>

<style lang="scss">
#nav {
  padding: 20px;
  display: flex;
  justify-content: center;
  a {
    font-weight: bold;
    color: #2c3e50;
    margin-right: 15px;
    padding-left: 15px;
    &:last-child {
      margin-right: 0;
    }

    &.router-link-exact-active {
      color: #42b983;
    }
  }
}
</style>

<script>
// import sidebar from "@/components/sidebar";
// import Todos from "./components/Todos";
// import appFooter from "@/components/Footer";
// import appHeader from "@/components/Header";
// import InputField from "@/components/Inputfield"
// import ability from "@/components/ability"

export default {
  components: {
    // sidebar,
    // Todos,
    // appFooter,
    // appHeader,
    // InputField,
    // ability
  },
  data() {
    return {
      // Todos: [
      //   {
      //     id: 1,
      //     title: "Todo one",
      //     completed: false,
      //     mes: "https://source.unsplash.com/random/400x400",
      //   },
      //   {
      //     id: 2,
      //     title: "Todo two",
      //     completed: true,
      //     mes: "https://source.unsplash.com/random/400x400",
      //   },
      //   {
      //     id: 3,
      //     title: "Todo false",
      //     completed: false,
      //     mes: "https://source.unsplash.com/random/400x400",
      //   },
      // ],
    };
  },
};
</script>
