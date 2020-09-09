<template id="">
  <div class="row justify-content-center">
      <div class="col-md-8">
          <form-component @new="addThought"></form-component>
          <br>
          <thougth-component
            v-for="(thougth, index) in thougths"
            :key="thougth.id"
            :thougth="thougth"
            @delete="deleteThougth(index)"
            >
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
    },
    methods:{
      addThought(thought){
        this.thougths.push(thought)
      },
      deleteThougth(index){
        this.thougths.splice(index, 1)
      }
    }
  }
</script>
