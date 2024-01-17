<script>
export default{
  data(){
    return {
      weatherData: [],
    };
  },
  mounted() {
    fetch('https://opendata.cwa.gov.tw/api/v1/rest/datastore/F-C0032-001?Authorization=CWA-1FF089FD-A66F-431A-970E-F9103900D0A5')
    .then(res =>{
      return res.json();
    })
    .then(result => {
      console.log(result);
      this.weatherData = result.records.location
    });
  },

}
</script>

<template>
  <div>
    {{ weatherData }}
  </div>
</template>

<style scoped="scss">
</style>