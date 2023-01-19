<template>

  <div id="app" :class="typeof weather.main != 'undefined' && weather.main.temp > 18 ? 'warm' : ''">
  
    <main>
      <div class="search-box">
        <input 
        type="text"  
        class="search-bar" 
        placeholder="Search..."
        v-model = "query"
        @keypress = "fetchWeather"
        />
      </div>

      <div class="weather-wrap" v-if ="typeof weather.main != 'undefined' " >

        <div class="location-box">
          <div class="location"> {{ weather.name }}, {{ weather.sys.country }}</div>
          <div class="date"> {{ dateBuilder() }}</div>
        </div>
        <div class="weather-box">
          <div class="temp"> {{ Math.round(weather.main.temp)}} °C</div>
          <div class="weather"> {{ weather.weather[0].description}}</div>
        </div>
      </div>
    </main>

  </div>
</template>

<script>


export default {

  name: 'app',
  data(){
    return{
      api_key: '465af90b1540b9ff8c6e6e5aa5fe175d',
       url_base: 'https://api.openweathermap.org/data/2.5/',
       query: '',
       weather: {}
    }
  },

  methods:{

    fetchWeather (e){
      if(e.key == "Enter"){
        fetch(`${this.url_base}weather?q=${this.query}&units=metric&APPID=${this.api_key}&lang=pt_br`)
        .then(res => {
          return res.json();
        }).then(this.setResults);
      }
    },
    setResults(results){
      this.weather = results;
    },
    dateBuilder(){
      let d = new Date();
      let months = ["Janeiro",  "Fevereiro", "Março", "Abril", "Maio", "Junho", "Julho", "Agosto", "Setembro", "Outubro", "Novembro", "Dezembro"]
      let days = ["Domingo", "Segunda-feira", "Terça-feira", "Quarta-feira", "Quinta-feira", "Sexta-feira", "Sábado"];

      let day = days[d.getDay()];
      let date = d.getDate();
      let month = months[d.getMonth()];
      let year =d.getFullYear();

      return `${day}, ${date} de ${month} de ${year}`;
    }
  }
  
}
</script>


<style>
@import "@/global.css";

</style>