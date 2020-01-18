<template>
  <div class="card bg-white">
    <div class="card-body d-flex align-items-center justify-content-between">
      <h4 class="mt-1 mb-1">Hi {{username}}, Welcomeback!</h4>
    </div>
  </div>
</template>

<script>
export default {
  name: "WelcomeMessage",
  data() {
    return {
      username: {}
    };
  },

  created() {
    fetch(
      "https://inlupp-fa.azurewebsites.net/api/users?firstname=Natasa&lastname=Kirin"
    )
      .then(res => res.text())
      .then(data => {
        this.username = data;
      });
  }
};
</script>

<style>
</style>