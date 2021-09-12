<template>
  <div class="users">
    <!-- <userpage msg="Welcome to Your userspage new ew" /> -->
    <!-- <h1>Users</h1> -->
    <!-- <router-link :to="{ name: 'usersProfile' }">profile</router-link> -->
    <router-view />
  </div>
</template>

<script>
// @ is an alias to /src
// import HelloWorld from "@/components/HelloWorld.vue"
// import Userpage from "../components/userpage.vue";

export default {
  name: "users",
  // @change="changeSomething"
  components: {
    // HelloWorld,
    // Userpage,
  },
};
</script>
