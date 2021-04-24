<template>
  <select v-model="selected" @change="onChange" class="block w-full p-3 mt-10 border rounded form-select">
    <option value="0" selected disabled>Select Country</option>
    <option v-for="country in countries" :value="country.ID">{{country.Country}}</option>
  </select>
</template>

<script>

export default {
  name: 'CountrySelect',
  props: ['countries'],
  data(){
    return {
      selected:0,
    }
  },
  methods: {
    onChange(){
      const country = this.countries.find((cty) => cty.ID === this.selected);
      console.log(country)
      this.$emit('get-country', country)
    }
  }
}

</script>