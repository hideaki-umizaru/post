<template>
  <div id="app">
    <input type="number" placeholder="000-0000" v-model="getNumber" />
    <button @click="sendPost">住所自動入力</button>
    <h2>Address:{{ show }}</h2>
  </div>
</template>

<script>
import axios from "axios";
export default {
  data() {
    return {
      getNumber: "",
      show: "",
    };
  },
  methods: {
    sendPost() {
      axios.get(`https://apis.postcode-jp.com/api/v4/postcodes/${this.getNumber}?apiKey=yO7TZrzN6bwf5fryzBCn5dXB7Llq4JhTtL0DnaH`)
      .then((res) => {
          this.show = res.data[0].allAddress;
          console.log(res.data[0].allAddress);
        });
  
    },
  },
};
</script>