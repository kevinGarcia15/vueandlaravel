<template id="">
  <div class="card">
    <div class="card-header">En que estas pensando?</div>

    <div class="card-body">
      <form class="" action="" v-on:submit.prevent="newThougth()">
        <div class="form-group">
          <label for="thogth">Ahora estoy pensando en:</label>
          <input
            type="text"
            class="form-control"
            name="thogth"
            value=""
            v-model="description">
        </div>
        <button type="submit"  class="btn btn-primary" name="button">
          Enviar Pensamiento
        </button>
      </form>
    </div>
  </div>
</template>
<script>
  export default{
    data(){
      return{
        description:''
      }
    },
    mounted(){
      console.log('Form Component is mouted')
    },
    methods:{
      newThougth(){
        let thougth = {
          id:2,
          description: this.description,
          created_at: '09/09/2020'
        }
        this.$emit('new', thougth)
        this.description = ''
      }
    }
  }
</script>
