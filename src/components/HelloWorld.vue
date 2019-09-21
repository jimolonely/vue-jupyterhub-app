<template>
  <div class="hello">
    <button @click="auth">open jupyterhub</button>
  </div>
</template>

<script>

import axios from 'axios';

export default {
  name: 'HelloWorld',
  data () {
    return {
      msg: 'Welcome to Your Vue.js App'
    }
  },
  methods:{
    auth(){
      axios({
        method:'get',
        url:'http://hub.jd.com:8000/',
        headers:{
          'Access-Control-Allow-Origin':'*',
          'Authorization': 'bearer eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJzdWIiOiIxMjM0NTY3ODkwIiwidXNlcm5hbWUiOiJqaW1vIiwiaWF0IjoxNTE2MjM5MDIyfQ.hdMd2TNqSY2EUVpv4HqofQN_jfSWjclk95cH7aoGseQ'
        }
      }).then(function(res){
          console.log(res)

      })
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h1, h2 {
  font-weight: normal;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
