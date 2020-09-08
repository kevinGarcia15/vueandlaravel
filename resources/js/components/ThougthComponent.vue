<template>
    <div class="container">
        <div class="card">
            <div class="card-header">Publicado en {{thougth.created_at}}</div>

            <div class="card-body">
                <p>
                    {{thougth.description}}
                </p>
            </div>
        </div>

        <div class="card">
            <div class="card-body">
                <button type="button" name="button" class="btn btn-default">
                    Editar
                </button>
                <button type="button" name="button" class="btn btn-danger">
                    Eliminar
                </button>
            </div>
        </div>
    </div>
</template>

<script>
export default {
  props: ['thougth'],
    data(){
      return{
        thougth:{
          id:'',
          description:'',
          created_at:''
        }
      }
    },
    mounted() {
        console.log("Component mounted.");
    }
};
</script>
