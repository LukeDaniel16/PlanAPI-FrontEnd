<template>
  <section>
    <div class="box" v-for="item in datasTeste" :key="item.id">
      <div class="notification">
        <div class="content">
          <p><b-icon icon="signature" size="is-small" /> {{ item.nome }}</p>
          <p><b-icon icon="stop" size="is-small" /> {{ item.statusTask }}</p>
          <p><b-icon icon="clock" size="is-small" /> {{ item.dataTasK }}</p>
          <p>
            <b-icon icon="envelope" size="is-small" />
            {{ item.emailResponsavel }}
          </p>
          <p>
            <b-icon icon="file-alt" size="is-small" /> {{ item.descricaoTask }}
          </p>
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

          <b-button type="is-success" outlined v-on:click="concluirTask"
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

          <b-button type="is-success" outlined v-on:click="cancelarTask"
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
    concluirTask() {},
    cancelarTask() {},
  },
  created() {
    console.log(localStorage.getItem('IdUsuarioLogado'), 'Chamou!')
    let teste = {
      id: 1,
      nome: 'AaAAAAa',
      statusTask: 'Pendente',
      dataTasK: '01/01/1991',
      emailResponsavel: 'viniiciiusmelo@gmail.com',
      descricaoTask: 'Descricao Primeira Task',
    }

    let teste2 = {
      id: 2,
      nome: 'BBBBB',
      statusTask: 'Pendente',
      dataTasK: '01/01/1992',
      emailResponsavel: 'viniiciiusmelo@gmail.com',
      descricaoTask: 'Descricao Segunda Task',
    }
    this.datasTeste.push(teste)
    this.datasTeste.push(teste2)

    console.log(this.datasTeste)

    console.log(this.$route.path)
  },
}
</script>

<style>
</style>