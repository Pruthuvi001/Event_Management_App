<template>
  <div class="header-frame">
    <h1 class="text-center mt-3 main-heading">Event Management System</h1>
  </div>
  <div class="container">
    <h2 class="text-center mt-3">Why Choose Us</h2>
    <div class="row">
      <div class="col-12 col-md-6 col-lg-4" v-for="item in items" :key="item.title">
        <div class="card">
          <div class="card-body">
            <h5 class="card-title">{{ item.title }}</h5>
            <p class="card-text">{{ item.description }}</p>
          </div>
        </div>
      </div>
    </div>
    <h2 class="text-center mt-3">Event Information</h2>
    <EventTable :events="events" />
    <h2 class="text-center mt-3">Registration Form</h2>
    <RegistrationForm :events="events" />
  </div>
</template>

<script>
import events from './components/events.json';
import EventTable from './components/EventTable.vue';
import RegistrationForm from './components/RegistrationForm.vue';

export default {
  data() {
    return {
      items: [
        { title: 'Efficient Event Planning', description: 'We handle everything from start to finish, ensuring seamless execution.' },
        { title: 'Expert Team', description: 'Our professionals bring years of experience to create successful events.' },
        { title: 'Cost-Effective Solutions', description: 'We provide budget friendly event management with payment plans.' },
        { title: 'On-Time Execution', description: 'Timely delivery is our priority to ensure a hassle-free experience.' },
        { title: 'High Customer Satisfaction', description: 'Our clients trust us for top-notch event experiences and services.' },
        { title: 'Strong Communication', description: 'We keep you informed throughout the process for a smooth experience.' },
      ],
      events
    }
  },
  components: {
    EventTable,
    RegistrationForm
  }
}
</script>

<style scoped>
.header-frame {
  display: flex;
  justify-content: center;
  border: 5px solid black; 
  background: black; 
  margin: 20px;
  padding: 20px;
}

.main-heading {
  color: #FFF5EE; 
  margin: 0; 
}

.card {
  transition: transform 0.3s ease-in-out;
}

.card:hover {
  transform: scale(1.05);
  box-shadow: 0px 0px 15px rgba(0, 0, 0, 0.2);
}

.container {
  padding: 20px;
  background: rgba(255, 255, 255, 0.8);
}

h1, h2 {
  color: #4a90e2; 
}
</style>