<template>
  <select 
    @change="onChange()"
    class="mt-10 form-select block w-full border p-3 rounded" 
    v-model="selected">
      <option value="0">Select Country</option>
      <option v-for="country in countries" :key="country.ID" :value="country.ID">{{ country.Country }}</option>
  </select>
</template>

<script>
export default {
    name: 'CountrySelect',
    data(){
        return{
            selected: 0
        }
    },
    props: ['countries'],
    methods: {
        onChange(){
            
            const selectedCountry = this.countries.find(item => item.ID === this.selected)

            this.$emit('get-country', selectedCountry)
        }
    }
}
</script>

<style>

</style>