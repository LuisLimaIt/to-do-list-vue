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
      <div v-for="tarefa, index in tarefas"
      :key="index">
        <ItemTarefa 
          :tarefa="tarefa"
        />  
      </div>

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
    data() {
      return {
        tarefas:[
          {titulo: "Ir ao mercado", concluido: false},
          {titulo: "Ir a academia", concluido: false},
          {titulo: "Comprar pão", concluido: false},
          {titulo: "Marcar consulta com o dentista", concluido: false},
          {titulo: "Estudar para o exame de programação", concluido: false},
        ]
      }
    }
  }
</script>
