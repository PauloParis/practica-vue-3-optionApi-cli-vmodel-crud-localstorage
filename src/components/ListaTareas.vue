<template>
  <div>
    <table class="table text-white">
      <thead>
        <tr>
          <th scope="col">#</th>
          <th scope="col">Nombre</th>
          <th scope="col">Categorias</th>
          <th scope="col">Estado</th>
          <th scope="col">Numero</th>
          <th scope="col">Acción</th>
        </tr>
      </thead>
      <tbody>
        <tr v-for="item in tareas" :key="item.id">
          <th scope="row">{{ item.id }}</th>
          <td>{{ item.nombre }}</td>
          <td>{{ item.categorias.join(", ") }}</td>
          <td>{{ item.estado }}</td>
          <td>{{ item.numero }}</td>
          <td>
            <button @click="deleteTareas(item.id)" class="btn btn-danger btn-sm">
                Eliminar
            </button>
            <RouterLink
                class="btn btn-warning ms-2 btn-sm"
                :to="{name: 'editar', params: {id:item.id}}">
                Editar
            </RouterLink>
          </td>
        </tr>
      </tbody>
    </table>
  </div>
</template>

<script>
import { mapActions, mapState } from "vuex";
export default {
  name: "Vue3OptionApiCliVmodelCrudLocalstorageListaTareas",

  computed: {
    ...mapState(["tareas"]),
  },
  methods: {
    ...mapActions(['deleteTareas'])
  }
};
</script>

<style lang="scss" scoped></style>
