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
        const params = {
          description: this.description
        };

        this.description = ''

        axios.post('/thoughts', params)
          .then((response)=>{
            const thougth = response.data;
            this.$emit('new', thougth)
          });
      }
    }
  }
</script>
