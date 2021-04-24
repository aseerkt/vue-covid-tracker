<template>
  <main v-if="!loading">
    <DataTitle :text='title' :dataDate='dataDate' />  

    <CountrySelect @get-country="getCountryData" :countries='countries' />
    <button v-if="stats.Country" @click="clearCountryData" class="block p-3 mx-auto mb-5 text-white uppercase bg-green-700 rounded focus:outline-none hover:bg-green-600">Get Global Data</button>  
    
    <DataBoxes :stats="stats" />

  </main>

  <main class="flex flex-col justify-center text-center align-middle" v-else>
    <div class="mt-10 mb-6 text-3xl text-gray-500">
      Fetching Data...
    </div>
    <img :src="loadingImage" class="w-24 m-auto" alt="">
  </main>  
</template>

<script>
// @ is an alias to /src
import DataTitle from '@/components/DataTitle.vue';
import DataBoxes from '@/components/DataBoxes.vue';
import CountrySelect from '../components/CountrySelect.vue';

export default {
  name: 'Home',
  components: {
    DataTitle,
    DataBoxes,
    CountrySelect
  },
  data () {
    return {
      loading: true,
      title: 'Global',
      dataDate: '',
      stats:{},
      countries: [],
    loadingImage: require('../assets/hourglass.gif'),
    }
  },
  methods: {
    async fetchCovidData() {
      const res = await fetch('https://api.covid19api.com/summary');
      return await res.json()
    },
    setCovidData(data){
      this.dataDate = data.Date;
      this.title = 'Global';
      this.stats = data.Global;
      this.countries = data.Countries
      this.loading = false;
    },
    getCountryData(country){
      this.stats = country;
      this.title = country.Country;
    },
    async clearCountryData(){
      this.loading = true;
      const data = await this.fetchCovidData();
      this.setCovidData(data);
    }
  },
  async created() {
    const data = await this.fetchCovidData();
    this.setCovidData(data);
  }
}
</script>
