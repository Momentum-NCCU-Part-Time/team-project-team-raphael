<template>
  <div>
    <h1>Weather App</h1>
    <label for="city">Enter City:</label>
    <input v-model="city" id="city" />
    <button @click="getWeather">Sign Up</button>
    <div v-if="weather">
      <h2>{{ weather.city }}</h2>
      <p>Temperature: {{ weather.temperature }}°C</p>
      <p>Description: {{ weather.description }}</p>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      city: '',
      weather: null,
    };
  },
  methods: {
    getWeather() {
      if (!this.city) return;
      <--ADD LINK HERE --->
      this.$axios.get(`http://LINKHERE!!!/weather?city=${this.city}`)
        .then(response => {
          this.weather = response.data;
        })
        .catch(error => {
          console.error('Error fetching weather:', error);
        });
    },
  },
};
</script>

<style>
/* Add your styles here */
</style>
