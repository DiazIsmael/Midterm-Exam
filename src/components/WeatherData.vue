<template>
    <hr class="hr" />
    <div>
        <h4>{{ data.location.name }} Weather Data in a Table</h4>
        <table class="table table-bordered">
            <thead>
                <tr>
                <!-- Weather Info Variables -->
                <th>Date</th>
                <th>Temperature (Celcius)</th>
                </tr>
            </thead>
            <tbody>
                <!-- Vue Loops Through All Response Data Days -->
                <tr v-for="(entry, index) in data.forecast.forecastday" :key="index">
                <td>{{ entry.date }}</td>
                <td>{{ entry.day.avgtemp_c }}</td>
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