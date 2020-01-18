<template>
  <a class="dropdown-item preview-item">
    <div class="preview-thumbnail">
      <div class="preview-icon" v-bind:class="titleColor(notification.title)">
        <i class="mdi mdi-information mx-0"></i>
      </div>
    </div>
    <div class="preview-item-content">
      <h6 class="preview-subject font-weight-normal">{{notification.title}}</h6>
      <p class="font-weight-light small-text mb-0 text-muted">{{notification.subtitle}}</p>
    </div>
  </a>
</template>

<script>
export default {
  name: "Notification",
  props: {
    notification: Object
  },
  methods: {
    titleColor: title => {
      switch (title) {
        case "Application Error":
          return "bg-success";

        case "Settings":
          return "bg-warning";

        case "New User Registration":
          return "bg-info";

        default:
          return "bg-secondary";
      }
    }
  }
};
</script>

<style>
</style>