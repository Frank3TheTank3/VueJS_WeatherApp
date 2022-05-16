<template>
  <div
    id="app"
    :class="
      typeof weather.main != 'undefined' && weather.main.temp > 16 ? 'hot' : ''
    "
  >
    <main>
      <div class="searchbox">
        <input
          type="text"
          class="searchbar"
          placeholder="Search..."
          v-model="query"
          @keypress="fetchWeather"
        />
      </div>
      <!-- -->
      <div class="weatherwrap" v-if="typeof weather.main != 'undefined'">
        <div class="locationbox">
          <div class="location">
            {{ weather.name }}, {{ weather.sys.country }}
          </div>
          <div class="date">{{ dateBuilder() }}</div>
        </div>

        <div class="weatherbox">
          <div class="temp">{{ Math.round(weather.main.temp) }}°C</div>
          <div class="weatherstatus">{{ weather.weather[0].main }}</div>
        </div>
      </div>
    </main>
  </div>
</template>
<script>
export default {
  name: "FrankVueApp",

  data() {
    return {
      apiKey: "8220c1a404b6f19c2dc7cd7e3144ed21",
      urlBase: "https://api.openweathermap.org/data/2.5/",
      query: "",
      weather: {},
    };
  },

  methods: {
    startweather() {
      fetch(`${this.urlBase}weather?q=Zurich&units=metric&APPID=${this.apiKey}`)
        .then((res) => {
          return res.json();
        })
        .then(this.setResults);
    },
  

  fetchWeather(e) {
    if (e.key == "Enter") {
      fetch(
        `${this.urlBase}weather?q=${this.query}&units=metric&APPID=${this.apiKey}`
      )
        .then((res) => {
          return res.json();
        })
        .then(this.setResults);
    }
  },

  setResults(results) {
    this.weather = results;
  },

  dateBuilder() {
    let d = new Date();
    let months = [
      "Januar",
      "Feburar",
      "März",
      "April",
      "Mai",
      "Juni",
      "Juli",
      "August",
      "September",
      "Oktober",
      "November",
      "Dezember",
    ];
    let days = [
      "Sonntag",
      "Montag",
      "Dienstag",
      "Mittwoch",
      "Donnerstag",
      "Freitag",
      "Samstag",
    ];

    let day = days[d.getDay()];
    let date = d.getDate();
    let month = months[d.getMonth()];
    let year = d.getFullYear();

    return `${day} ${date} ${month} ${year}`;
  }
  
},

 beforeMount(){
    this.startweather()
 },
}
</script>

<style>
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

body {
  font-family: "Franklin Gothic Medium", "Arial Narrow", Arial, sans-serif;
}

#app {
  background-image: url("./assets/cold.jpg");
  background-size: cover;
  background-position: bottom;
  transition: 0.4s;
}

#app.hot {
  background-image: url("./assets/hot.jpg");
}

main {
  min-height: 100vh;
  padding: 25px;
  background-image: linear-gradient(
    to bottom,
    rgba(0, 0, 0, 0.25),
    rgba(0, 0, 0, 0.75)
  );
}

.searchbox {
  width: 100%;
  margin-bottom: 30px;
}

.searchbox .searchbar {
  display: block;
  width: 100%;
  padding: 15px;

  color: #313131;
  font-size: 20px;

  appearance: none;
  border: none;
  outline: none;
  background: none;

  box-shadow: rgba(0, 0, 0, 0.25);
  background-color: rgba(255, 255, 255, 0.5);
  border-radius: 16px, 0px, 16px, 0px;
}

.locationbox .location {
  color: #fff;
  font-size: 32px;
  font-weight: 500;
  text-align: center;
  text-shadow: 1px 3px rgba(0, 0, 0, 0.25);
}

.locationbox .date {
  color: #fff;
  font-size: 20px;
  font-weight: 300;
  font-style: italic;
  text-align: center;
}

.weatherbox {
  text-align: center;
}

.weatherbox .temp {
  display: inline-block;
  padding: 10px 25px;
  color: #fff;
  font-size: 102px;
  font-weight: 900;

  text-shadow: 3px 6px rgba(0, 0, 0, 0.25);
  background-color: rgba(255, 255, 255, 0.25);
  border-radius: 16px;
  margin: 30px 0px;

  box-shadow: 3px 6px rgba(0, 0, 0, 0.25);
}

.weatherbox .weather {
  color: #fff;
  font-size: 48px;
  font-weight: 700;
  font-style: italic;
  text-shadow: 3px 6px rgba(0, 0, 0, 0.25);
}
</style>
