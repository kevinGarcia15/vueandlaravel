<template id="">
  <div class="row justify-content-center">
      <div class="col-md-8">
          <form-component></form-component>
          <br>
          <thougth-component
            v-for="thougth in thougths"
            :key="thougth.id"
            :thougth="thougth">
          </thougth-component>
      </div>
  </div>
</template>

<script>
  export default{
    data(){
      return {
        thougths:[{
          'id': 1,
          'description': 'abc',
          'created_at': '01/09/2020'
        }]
      }
    },
    mounted(){
        console.log('Component thouth mounted')
    }
  }
</script>
