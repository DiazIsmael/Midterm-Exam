<template>
   <div class="row justify-content-center">
        <div class="col-md-6">
            <h2 class="text-center">Weather Data</h2>
            <h3 class="text-center">Please fill in the form and use the submit button to load data.</h3>
            <!-- Weather Query Form -->
            <form @submit.prevent="handleUpdateForm">
                <div class="form-group">
                    <label>Location*</label>
                    <input v-model="Location" type="location" class="form-control" required>
                </div>

                <div class="form-group">
                    <label>Query Start Date*</label>
                    <input v-model="startDate" type="date" class="form-control" required>
                </div>

                <div class="form-group">
                    <label>Query End Date*</label>
                    <input v-model="endDate" type="date" class="form-control" required>
                </div>

                <button class="btn btn-danger mt-3">Get Weather Data :D</button>
            </form>
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
      endDate: ''
    };
  },
  methods: {
    async submitForm() {
      // working on ir
    }
  },
  components: {
    WeatherData
  }
};
</script>