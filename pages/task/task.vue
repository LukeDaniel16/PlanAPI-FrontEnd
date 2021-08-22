<template>
  <div class="columns">
    <div class="column">

      <b-field label="Nome" label-position="inside">
        <b-input v-model="nomeTask" />
      </b-field>

      <b-field label="Status" label-position="inside">
        <b-input v-model="statusTask" disabled/>
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
            <b-button v-on:click="salvarTask" type="is-primary" expanded icon-right="save">Salvar</b-button>
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
    salvarTask() {
      
    },
  },
  created() {
  },
}
</script>
<style>
</style>