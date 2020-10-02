<template>
  <div>
    <img :src="flag" alt="">
    {{ country }}
    <th class="text-left">
      todayCases ={{ todayCases }}
    </th><br>
    <th class="text-left">
      todayDeaths ={{ todayDeaths }}
    </th><br>
    <th class="text-left">
      todayRecovered={{ todayRecovered }}
    </th><br>
    <th class="text-left">
      death={{ death }}
    </th><br>
    <th class="text-left">
      active={{ active }}
    </th><br>
    <th class="text-left">
      activePerOneMillion ={{ activePerOneMillion }}
    </th><br>
    <th class="text-left">
      cases ={{ cases }}
    </th><br>
    <th class="text-left">
      continent={{ continent }}
    </th><br>
    <th class="text-left">
      country= {{ country }}
    </th>
  </div>
</template>

<script>
export default {
  data () {
    return {
      country: this.$route.params.id.country,
      todayCases: this.$route.params.id.todayCases,
      todayDeaths: this.$route.params.id.todayDeaths,
      todayRecovered: this.$route.params.id.todayRecovered,
      deaths: this.$route.params.id.deaths,
      active: this.$route.params.id.active,
      activePerOneMillion: this.$route.params.id.activePerOneMillion,
      cases: this.$route.params.id.cases,
      continent: this.$route.params.id.continent
    }
  }

}
</script>

<style>
</style>
