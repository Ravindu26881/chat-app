<template>
  <div class="about">
    <h1>This is an about spage</h1>
    <button @click="api">sss</button>
    <br>
    <div style="display: flex;
                flex-direction: column;">
      <div style="display: flex;
                  flex-direction: row;
                  justify-content: space-between;"
            v-for="item in list" :key="item">
        <div>{{list[0].Nation}}</div>
        <div>{{list[0].Year}}</div>
        <div>{{list[0].Population}}</div>
      </div>
    </div>
  </div>
</template>

<script>
import axios from "axios";

export default {
  name: 'About',
  data () {
    return {
      list: {}
    }
  },
  methods: {
    api () {
      console.log('clicked')
      const options = {
        method: 'GET',
        url: 'https://datausa.io/api/data?drilldowns=Nation&measures=Population',  
      };
      axios.request(options).then((response) => {
        console.log(response.data.data)
        this.list = response.data.data
        console.log('list' , this.list)
      }).catch((error) => {
        console.error(error)
      });
    }
  }
}
</script>