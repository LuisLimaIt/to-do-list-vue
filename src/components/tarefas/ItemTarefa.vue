<template>
  <div>
      <v-list-item
      :class="{'light-blue lighten-4' : tarefa.concluido}"
      @click="handleChange"
      >
        <template v-slot:default="{}">
            <v-list-item-action>
              <v-checkbox :input-value="tarefa.concluido"></v-checkbox>
            </v-list-item-action>

            <v-list-item-content>
              <v-list-item-title
              :class="{'text-decoration-line-through' : tarefa.concluido}"
              >{{tarefa.titulo}}</v-list-item-title>
            </v-list-item-content>

            <v-list-item-action>
              <v-btn 
              icon
              @click.stop="handleRemoveTask(tarefa.id)"
              >
                <v-icon color="red darken-2">mdi-trash-can</v-icon>
              </v-btn>
            </v-list-item-action>
          </template>
        </v-list-item>
        <v-divider />
  </div>
</template>

<script>
export default {
  props:["tarefa"],
  methods: {
    handleChange() {
      // eslint-disable-next-line vue/no-mutating-props
      this.tarefa.concluido = !this.tarefa.concluido
    },
    handleRemoveTask(id) {
      this.$store.commit('removeTask', id)
    }
  }
}
</script>

<style>

</style>