<template>
  <section>
    <div class="box" v-for="item in datasTeste" :key="item.id">
      <div class="notification">
        <div class="content">
          <p><b-icon icon="signature" size="is-small" /> {{ item.nome }}</p>
          <p><b-icon icon="stop" size="is-small" /> {{ item.status }}</p>
          <p>
            <b-icon icon="clock" size="is-small" /> {{ item.prazoConclusao }}
          </p>
          <p>
            <b-icon icon="envelope" size="is-small" />
            {{ item.emailAssociado }}
          </p>
          <p><b-icon icon="file-alt" size="is-small" /> {{ item.descricao }}</p>
        </div>

        <b-modal v-model="mostrarModalConclusao" :width="640">
          <h6>Concluir Task</h6>
          <br />
          <b-field>
            <b-input
              placeholder="Descricão Conclusão"
              v-model="descricaoConclusao"
              maxlength="200"
              type="textarea"
            ></b-input>
          </b-field>

          <b-button type="is-success" outlined v-on:click="concluirTask(item)"
            >Concluir
          </b-button>
        </b-modal>

        <!-- Modal Cancelamento -->
        <b-modal v-model="mostrarModalCancelamento" :width="640">
          <h6>Cancelar Task</h6>
          <br />
          <b-field>
            <b-input
              placeholder="Descricão Cancelamento"
              v-model="descricaoCancelamento"
              maxlength="200"
              type="textarea"
            ></b-input>
          </b-field>

          <b-button type="is-success" outlined v-on:click="cancelarTask(item)"
            >Concluir
          </b-button>
        </b-modal>

        <div class="buttons">
          <b-button
            type="is-success"
            outlined
            v-on:click="mostrarModalConclusao = true"
            >Concluir
          </b-button>

          <b-button
            v-on:click="mostrarModalCancelamento = true"
            type="is-danger"
            outlined
            >Cancelar</b-button
          >
        </div>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  data() {
    return {
      datasTeste: [],
      mostrarModalConclusao: false,
      mostrarModalCancelamento: false,
      descricaoConclusao: '',
      descricaoCancelamento: '',
    }
  },
  methods: {
    async concluirTask(item) {
      let agendamento = item
      console.log(agendamento)

      try {
        const data = await this.$axios.$put(
          'https://localhost:44309/api/usuarios/login'
        )

        this.mensssageSucess('Concluído com Sucesso')
        this.$router.push(this.$route.path)
      } catch (error) {
        mensssageError('Erro ao Concluir Task')
      }
    },
     async cancelarTask(item) {

      let agendamento = item
      console.log(agendamento)

      try {
        const data = await this.$axios.$put(
          'https://localhost:44309/api/usuarios/login'
        )

        this.mensssageSucess('Cancelado com Sucesso')
        this.$router.push(this.$route.path)
      } catch (error) {
        mensssageError('Erro ao Cancelar Task')
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
    async buscarTasks() {
      let idUsuario = localStorage.getItem('IdUsuarioLogado')
      console.log(this.$route.path)
      let paraMim = this.$route.path == '/task/paraMim'

      try {
        const data = await this.$axios.$post(
          'https://localhost:44309/api/task/buscarTasks/' +
            idUsuario +
            '/' +
            paraMim
        )

        this.datasTeste = data
      } catch (error) {}
    },
  },
  created() {
    this.buscarTasks()
  },
}
</script>

<style>
</style>