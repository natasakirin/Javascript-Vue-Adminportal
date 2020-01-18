<template>
  <div class="card">
    <div class="card-body">
      <div class="d-flex justify-content-between align-items-md-end flex-wrap">
        <p class="card-title">Tickets</p>
        <div class="dropdown mb-3 mb-md-0">
          <button
            class="btn btn-sm btn-outline-light dropdown-toggle text-dark"
            type="button"
            id="dropdownMenuDate1"
            data-toggle="dropdown"
            aria-haspopup="true"
            aria-expanded="true"
          >{{ selectedYear.year }}</button>
          <div class="dropdown-menu dropdown-menu-right" aria-labelledby="dropdownMenuDate1">

            <button
              v-for="dropdownMenuYear of tickets"
              :key="dropdownMenuYear.year"
              v-on:click="selectedYear = dropdownMenuYear"
              class="dropdown-item"
            >{{ dropdownMenuYear.year }}</button>


          </div>
        </div>
      </div>
      <div class="table-responsive">
        <table class="table tickets-table mb-2">
          <thead>
            <th class="text-muted pl-0">Name</th>
            <th></th>
            <th class="text-muted">Date</th>
            <th class="text-muted">Projects</th>
          </thead>
          <tbody>
            <Ticket
              :key="ticket.name"
              v-for="ticket of selectedYear.tickets"
              :ticket="ticket"
            />
          </tbody>
        </table>
      </div>
    </div>
  </div>
</template>

<script>
import Ticket from "./Ticket";

export default {
  name: "Tickets",
  components: {
    Ticket
  },
  data() {
    return {
      tickets: [],
      selectedYear: []
    };
  },
  created() {
    fetch("https://inlupp-fa.azurewebsites.net/api/tickets")
      .then(res => res.json())
      .then(data => {
        this.tickets = data;
        this.selectedYear = data[data.length - 1];
      });
  }
};
</script>

<style>
</style>
