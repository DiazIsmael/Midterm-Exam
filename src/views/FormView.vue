<template>
   <div class="row justify-content-center">
        <div class="col-md-6">
            <h2 class="text-center">Weather Data</h2>
            <h5 class="text-center">Please fill in the form and use the submit button to load data.</h5>
            <!-- Weather Query Form -->
            <form @submit.prevent="handleUpdateForm">
                <div class="form-group">
                    <label>Location*</label>
                    <input v-model="location" type="text" class="form-control" required>
                </div>

                <div class="form-group">
                    <label>Query Start Date*</label>
                    <input v-model="startDate" type="date" class="form-control" required>
                </div>

                <div class="form-group">
                    <label>Query End Date (Can only access last 7 days)</label>
                    <input v-model="endDate" type="date" class="form-control">
                </div>

                <button type="submit" class="btn btn-danger mt-3">Get Weather Data :D</button>
            </form>
        </div>
        <div class="col-md-6">
            <WeatherData v-if="weatherData" :data="weatherData" />
        </div>
    </div>
</template>

<script>
import axios from "axios";
import WeatherData from "../components/WeatherData.vue";

export default {
  data() {
    return {
      location: '',
      startDate: '',
      endDate: '',
      weatherData: null, // will store the weather api data
      error: null, // may store weather api call errors
    };
  },
  methods: {
    async submitForm() {
      try {
        const response = await axios.get('https://weatherapi-com.p.rapidapi.com/history.json', {
          params: {
            q: this.location,
            dt: this.startDate, // Passed through user form input
            end_dt: this.endDate, // Optional, but allows for data retrieval for multiple days
          },
          headers: {
            'x-rapidapi-key': 'fa3316ce43msh2cab039c71264dfp19da5djsn3c504b0693e3',
            'x-rapidapi-host': 'weatherapi-com.p.rapidapi.com',
          },
        });

        this.weatherData = response.data;
        console.log(response.data);
      } 
      catch (error) {
        this.error = error;
        console.error('There was an error!', error);
      }
    },
  },
  components: {
    WeatherData
  }
};
</script>