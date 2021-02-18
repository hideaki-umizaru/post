<template>
  <div id="app">
  <input type="number" placeholder="000-0000" v-model="getNumber">
  <button @click="sendPost">住所自動入力</button>
  <h2>Address:{{show}}</h2>
  </div>
</template>

<script>
import axios from "axios";
const axios = require('axios');

export default {
  data () {
    return {
      getNumber:"",
      show:""
    };
  },
  methods:{
  sendPost() { 
  　const response = await 
    axios.get(`https://apis.postcode-jp.com/api/v4/postcodes/0123456?true=yO7TZrzN6bwf5fryzBCn5dXB7Llq4JhTtL0DnaH`);
  }
  }
};
</script>