<template>
  <div class="col-12">
    <v-row>
      <v-text-field v-model="textSearch" outlined type="text" />
      <div class="col-2">
        <v-btn @click="getitem()">
          search
        </v-btn>
      </div>
    </v-row>
    <nuxt-link :to="{ name: 'product-id' ,params: {id:tmp}} ">
      {{ country }}
    </nuxt-link>
  </div>
</template>
<script>
import axios from 'axios'
export default {
  data () {
    return {
      textSearch: null,
      death: '',
      active: '',
      todayCases: '',
      todayDeaths: '',
      todayRecovered: '',
      updated: '',
      continent: '',
      country: '',
      flag: '',
      tmp: ''
    }
  },
  methods: {
    getitem () {
      axios
        .get('https://corona.lmao.ninja/v2/countries/' + this.textSearch)
        .then((res) => {
          this.death = res.data.deaths
          this.active = res.data.active
          this.activePerOneMillion = res.data.activePerOneMillion
          this.todayCases = res.data.todayCases
          this.todayDeaths = res.data.todayDeaths
          this.todayRecovered = res.data.todayRecovered
          this.cases = res.data.cases
          this.continent = res.data.continent
          this.country = res.data.country
          this.flag = res.data.countryInfo.flag
          this.tmp = res.data
          // eslint-disable-next-line no-console
          console.log(this.flag)
        })
        .catch((err) => {
          // eslint-disable-next-line no-console
          console.error(err)
        })
    }
  }
}
</script>
<style>
#CV {
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #ffffff;
  background-color: rgb(77, 76, 73);
  position: center;
}
</style>
