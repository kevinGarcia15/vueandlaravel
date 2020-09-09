<template>
    <div class="container">
        <div class="card">
            <div class="card-header">Publicado en {{thougth.created_at}}</div>

            <div class="card-body">
                <input
                  type="text"
                  class="form-control"
                  v-if="editMode"
                  v-model="thougth.description">
                <p v-else>
                    {{thougth.description}}
                </p>
            </div>
        </div>

        <div class="card">
            <div class="card-body">
                <button
                  type="button"
                  name="button"
                  class="btn btn-default"
                  v-if="editMode"
                  v-on:click="onClickUpdate()">
                  Guardar Cambios
                </button>
                <button
                  v-else
                  type="button"
                  name="button"
                  class="btn btn-default"
                  v-on:click="onClickEdit()">
                    Editar
                </button>
                <button
                  type="button"
                  name="button"
                  class="btn btn-danger"
                  v-on:click="onClickDelete()">
                    Eliminar
                </button>
            </div>
        </div>
    </div>
</template>

<script>
export default {
  props: ['thougth'],
  data() {
    return {
      editMode: false
    };
  },
  mounted() {
    console.log('Component mounted.');
  },
  methods:{
    onClickDelete(){
      this.$emit('delete')
    },
    onClickEdit(){
      this.editMode = true
    },
    onClickUpdate(){
      this.editMode = false
      this.$emit('update', thought)
    }
  },
};

</script>
