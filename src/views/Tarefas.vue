<template>
  <div>
    <v-list
      flat
      subheader
    >
      <v-list-item-group
        v-model="settings"
        multiple
        active-class=""
      >
        <ItemTarefa />  

      </v-list-item-group>
    </v-list>
  </div>
</template>

<script>
  import ItemTarefa from '../components/tarefas/ItemTarefa.vue'
  export default {
    name: 'HomeView',

    components: {
      ItemTarefa
    },
  }
</script>
