<template>
  <div id="app">
  </div>
</template>

<script>
import axios from 'axios'

export default {
  name: "app",
  methods: {
    get() {
      axios.get(`https://api.spreadshirt.net/api/v1/shops/100560058/`, {
        crossDomain: true,
        headers: {
          'Access-Control-Allow-Origin' : '*',
          'Access-Control-Allow-Credentials': true,
          'Access-Control-Allow-Methods': 'GET, POST, OPTIONS, PUT',
          'Access-Control-Allow-Headers': 'X-PINGOTHER,Origin,X-Requested-With,Content-Type,Accept,Accept-Encoding,DNT',
          'Content-Type': 'application/json;charset=utf-8',
          "authorization": 'SprdAuth apiKey="fafd8c65-9419-49bd-bd48-3b9fde54830e"'
        }
      })
      .then(response => {
        console.log(response);
        console.log("test");
      })
      .catch(error => {
        // console.log(error);
      });
    },
  },
  mounted () {
    console.log('test');
    this.get();
  }
};
</script>
