<template>
    <div>
      <h2>Weather Data</h2>
      <table>
        <thead>
          <tr>
            <!-- Weather Info Variables -->
            <th>Date</th>
            <th>Temperature</th>
          </tr>
        </thead>
        <tbody>
          <tr v-for="(entry, index) in data.forecast" :key="index">
            <td>{{ entry.date }}</td>
            <td>{{ entry.temp }}</td>
          </tr>
        </tbody>
      </table>
    </div>
  </template>
  
  <script>
  export default {
    props: {
      data: {
        type: Object,
        required: true,
      },
    },
  };
  </script>