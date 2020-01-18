<template>
  <tr>
    <td class="pl-0">
      <div class="icon-rounded-md" v-bind:class="initialsColor(ticket.other)">
        <h4 class="font-weight-medium">{{getInitials(ticket.name)}}</h4>
      </div>
    </td>
    <td>
      <p class="mb-0">{{ ticket.name }}</p>
      <p class="text-muted mb-0">{{ ticket.city }}</p>
    </td>
    <td>
      <p class="mb-0">{{ getDate(ticket.date) }}</p>
      <p class="text-muted mb-0">{{ getTime(ticket.date) }}</p>
    </td>
    <td>
      <p class="mb-0">{{ ticket.project }}</p>
      <p class="text-muted mb-0">{{ ticket.other }}</p>
    </td>
    <td class="pr-0">
      <i class="mdi mdi-dots-horizontal icon-sm cursor-pointer"></i>
    </td>
  </tr>
</template>

<script>
export default {
  name: "Ticket",
  props: {
    ticket: Object
  },

  methods: {
    getInitials: name => {
      let names = name.split(" ");
      let initials = names[0][0] + names[1][0];
      return initials;
    },
    getDate: date => {
      let datetime = date.split(", ");
      let dateOnly = datetime[0];
      return dateOnly;
    },
    getTime: date => {
      let datetime = date.split(", ");
      let time = datetime[1];
      return time;
    },
    initialsColor: other => {
      switch (other) {
        case "View on map":
          return "icon-rounded-primary";

        case "Start session":
          return "icon-rounded-info";

        case "End session":
          return "icon-rounded-danger";

        case "On Way":
          return "icon-rounded-warning";

        default:
          return "icon-rounded-secondary";
      }
    }
  }
};
</script>

<style>
</style>