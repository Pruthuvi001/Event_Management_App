<template>
  <div>
    <input v-model="search" placeholder="Search events..." class="search-input">
    <table class="table">
      <thead>
        <tr>
          <th>Event ID</th>
          <th>Event Name</th>
          <th>Category</th>
          <th>Duration Hours</th>
        </tr>
      </thead>
      <tbody>
        <tr v-for="event in filteredEvents" :key="event.eventid">
          <td>{{ event.eventid }}</td>
          <td>{{ event.eventname }}</td>
          <td>{{ event.category }}</td>
          <td>{{ event.durationhour }}</td>
        </tr>
      </tbody>
    </table>
  </div>
</template>

<script>
import events from './events.json';

export default {
  data() {
    return {
      search: '',
      events
    };
  },
  computed: {
    filteredEvents() {
      return this.events.filter(event => event.eventname.toLowerCase().includes(this.search.toLowerCase()));
    }
  }
}
</script>

<style scoped>
.search-input {
  margin-bottom: 10px;
  width: 100%;
  padding: 8px 10px;
  font-size: 16px;
  border: 2px solid #ccc;
}

.table {
  width: 100%;
  border-collapse: collapse;
  margin-top: 10px;
}

.table th {
  background-color: #4CAF50;
  color: white;
}

.table th, .table td {
  padding: 8px;
  text-align: left;
  border-bottom: 1px solid #ddd;
}

.table tbody tr:nth-child(odd) {
  background-color: #f9f9f9;
}

.table tbody tr:hover td {
  background-color: #4a90e2; 
}

.table th {
  height: 50px;
}
</style>