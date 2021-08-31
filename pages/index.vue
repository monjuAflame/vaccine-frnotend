<template>
  <div>
    <h1 v-if="apiValue">Check: {{ apiValue }}</h1>
    <button @click.prevent="getBackendRequest()" >click</button>
  <Tutorial/>
  </div>
</template>

<script>
export default {
  data(){
    return {
      apiValue: ''
    }
  },

  mounted(){
    // this.getBackendRequest();
  },

  methods: {
    getBackendRequest(){
      this.$axios.get('test').then(res => {
        this.apiValue = res.data;
      })
    }
  }

  
}
</script>
