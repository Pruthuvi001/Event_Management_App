<template>
  <div>
    <form @submit.prevent="submitForm">
      <div class="form-group">
        <label for="username">Username:</label>
        <input type="text" id="username" v-model="username" class="form-control">
      </div>
      <div class="form-group">
        <label for="password">Password:</label>
        <input type="password" id="password" v-model="password" class="form-control">
      </div>
      <div class="form-group">
        <label for="confirmPassword">Confirm Password:</label>
        <input type="password" id="confirmPassword" v-model="confirmPassword" class="form-control">
        <p v-if="password !== confirmPassword" class="password-error">Passwords do not match</p>
      </div>
      <div class="form-group">
        <label for="category">Category:</label>
        <select id="category" v-model="selectedCategory" class="form-control" @change="updateEvents">
          <option value="Technology">Technology</option>
          <option value="Business">Business</option>
          <option value="Marketing">Marketing</option>
          <option value="Finance">Finance</option>
        </select>
      </div>
      <div class="form-group">
        <label for="event">Event:</label>
        <select id="event" v-model="selectedEvent" class="form-control">
          <option v-for="event in filteredEvents" :key="event.eventid" :value="event.eventname">{{ event.eventname }}</option>
        </select>
      </div>
      <button type="submit" class="btn btn-primary">Register</button>
    </form>
    <div v-if="submitted">
      <p>Registration Summary:</p>
      <p>Username: {{ username }}</p>
      <p>Selected Category: {{ selectedCategory }}</p>
      <p>Selected Event: {{ selectedEvent }}</p>
    </div>
  </div>
</template>

<script>  
import events from './events.json'; 

export default {
  data() {
    return {
      username: '',
      password: '',
      confirmPassword: '',
      selectedCategory: 'Business', 
      selectedEvent: '',
      filteredEvents: [],
      submitted: false
    };
  },
  mounted() {
    this.updateEvents();
  },
  methods: {
    updateEvents() {
      this.filteredEvents = events.filter(event => event.category === this.selectedCategory);
      if (this.filteredEvents.length > 0) {
        this.selectedEvent = this.filteredEvents[0].eventname;
      }
    },
    submitForm() {
      if (this.password === this.confirmPassword) {
        this.submitted = true;
      } else {
        alert('Passwords do not match');
      }
    }
  }
}
</script>

<style scoped>
.form-group {
  margin-bottom: 1rem;
}

label {
  display: block;
  margin-bottom: 0.5rem;
}

.form-control {
  display: block;
  width: 100%;
  padding: 0.375rem 0.75rem;
  font-size: 1rem;
  line-height: 1.5;
  color: #495057;
  background-color: #fff;
  background-clip: padding-box;
  border: 1px solid #ced4da;
  border-radius: 0.25rem;
  transition: border-color 0.15s ease-in-out, box-shadow 0.15s ease-in-out;
}

.form-control:focus {
  border-color: #80bdff;
  outline: 0;
  box-shadow: 0 0 0 0.2rem rgba(0, 123, 255, 0.25);
}

.btn-primary {
  color: #fff;
  background-color: #007bff;
  border-color: #007bff;
}

.btn-primary:hover {
  background-color: #0056b3;
  border-color: #004085;
}

.password-error {
  color: #dc3545;
  font-size: 0.875em;
}
</style>