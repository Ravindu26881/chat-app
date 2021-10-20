<template>
<div>
  <div >
    <h1>Enter your name to calculate your age</h1>
    <input id="name-input"/>
  </div>

  <button type="button" class="btn btn-primary" @click="clicked" data-toggle="modal" data-target="#exampleModal">
  calculate
</button>

<div style="color: black;" class="modal fade" id="exampleModal" tabindex="-1" role="dialog" aria-labelledby="exampleModalLabel" aria-hidden="true">
  <div class="modal-dialog" role="document">
    <div class="modal-content">
      <div class="modal-header">
        <h5 class="modal-title" id="exampleModalLabel" v-if="nameFieldEmpty === false">Hi {{name}}</h5>
        <button type="button" class="close" data-dismiss="modal" aria-label="Close">
          <span aria-hidden="true">&times;</span>
        </button>
      </div>
      <div class="modal-body">
        <h4 v-if="nameFieldEmpty === false"> Your age is {{list.age}} </h4>
        <h4 v-if="nameFieldEmpty === true"> Enter your name to calculate your age </h4>
      </div>
      <div class="modal-footer">
        <button type="button" class="btn btn-secondary" data-dismiss="modal">Close</button>
      </div>
    </div>
  </div>
</div>
</div>
</template>

<script>
import axios from "axios";

export default {
  name: 'Settings',
  data () {
    return {
      name: '',
      list: {},
      nameFieldEmpty: false
    }
  },
  methods: {
    clicked () {
      let inputValue = document.getElementById('name-input').value
      if (inputValue.length > 0) {
        this.nameFieldEmpty = false
        this.name = inputValue
        document.getElementById('name-input').value = ''
        this.api()
      }
      if (inputValue.length === 0) {
        this.nameFieldEmpty = true
      }
    },
    api () {
      console.log('clicked')
      const options = {
        method: 'GET',
        url: 'https://api.agify.io/?name=' + this.name,  
      };
      axios.request(options).then((response) => {
        console.log(response.data)
        this.list = response.data
        console.log('list' , this.list)
      }).catch((error) => {
        console.error(error)
      });
    }
  }
}
</script>
