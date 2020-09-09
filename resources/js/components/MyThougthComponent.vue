<template id="">
  <div class="row justify-content-center">
      <div class="col-md-8">
          <form-component @new="addThought"></form-component>
          <br>
          <thougth-component
            v-for="(thougth, index) in thougths"
            :key="thougth.id"
            :thougth="thougth"
            @update="updateThouht(index, ...arguments)"
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
        thougths:[]
      }
    },
    mounted(){
      axios.get('/thoughts')
        .then((response)=>{
          this.thougths = response.data;
        })
    },
    methods:{
      addThought(thought){
        this.thougths.push(thought)
      },
      deleteThougth(index){
        this.thougths.splice(index, 1)
      },
      updateThouht(index, thought){
        this.thougths[index] = thought
      }
    }
  }
</script>
