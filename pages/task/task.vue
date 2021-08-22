<template>
  <div class="columns">
    <div class="column">
      <b-field label="Nome" label-position="inside">
        <b-input v-model="nomeTask" />
      </b-field>

      <b-field label="Status" label-position="inside">
        <b-input v-model="statusTask" disabled />
      </b-field>

      <b-field label="Prazo para conclusão" label-position="inside">
        <b-datepicker placeholder="Click to select..." v-model="dataTasK">
        </b-datepicker>
      </b-field>

      <b-field label="Email Responsável" label-position="inside">
        <b-input type="email" v-model="emailResponsavel"> </b-input>
      </b-field>

      <b-field label="Descrição" label-position="inside">
        <b-input v-model="descricaoTask" type="textarea"></b-input>
      </b-field>

      <div class="buttons">
        <b-button
          v-on:click="salvarTask"
          type="is-primary"
          expanded
          icon-right="save"
          >Salvar</b-button
        >
      </div>
    </div>
  </div>
</template>

<script>
export default {
  layout: 'task/layoutTask',
  data() {
    return {
      nomeTask: '',
      descricaoTask: '',
      statusTask: 'Pendente',
      dataTasK: new Date(),
      emailResponsavel: '',
    }
  },
  methods: {
    async salvarTask() {
      let idUsuario = localStorage.getItem('IdUsuarioLogado')

      let objectTask = {
        Nome: this.nomeTask,
        PrazoConclusao: this.dataTasK,
        Descricao: this.descricaoTask,
        EmailAssociado: this.emailResponsavel,
      }

      try {
        const data = await this.$axios.$post(
          'https://localhost:44309/api/task/salvartask/' + idUsuario,
          objectTask
        )
        this.mensssageSucess('Task Criada Com Sucesso')
        this.$router.push('/task/porMim')
      } catch (error) {
        mensssageError('Erro ao criar Task')
      }
    },
    mensssageSucess(mensagem) {
      this.$buefy.toast.open({
        message: mensagem,
        type: 'is-success',
      })
    },
    mensssageError(mensagem) {
      this.$buefy.toast.open({
        message: mensagem,
        type: 'is-danger',
      })
    },
  },
  created() {},
}
</script>
<style>
</style>