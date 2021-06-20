<template>
  <section class="section is-medium">
    <div class="container">
      <div class="columns is-mobile is-centered">
        <div class="column is-4">
          <div class="box">
            <div class="columns is-mobile is-centered">
              <div class="column is-7">
                <b-image
                  :src="require('@/assets/images/logoPLan1.png')"
                  alt="PLan logo"
                ></b-image>
              </div>
            </div>
            <form @submit.prevent="cadastrarUsuario">
              <b-field label="Nome" label-position="inside" class="my-1">
                <b-input
                  placeholder="Ex: João de Barro"
                  maxlength="160"
                ></b-input>
              </b-field>
              <b-field label="Apelido" label-position="inside" class="my-1">
                <b-input placeholder="Joaozinho" maxlength="120"></b-input>
              </b-field>
              <b-field label="E-mail" label-position="inside" class="my-1">
                <b-input
                  placeholder="joao.barro@gmail.com"
                  type="email"
                  maxlength="60"
                  icon="envelope-square"
                ></b-input>
              </b-field>
              <b-field label="Senha" label-position="inside" class="my-1">
                <b-input type="password" maxlength="30"></b-input>
              </b-field>
              <div class="block has-text-centered my-1">
                <b-button
                  native-type="submit"
                  type="is-primary is-outlined"
                  expanded
                  icon-right="user-plus"
                >
                  <strong>Cadastrar</strong></b-button
                >
              </div>
            </form>
            <div class="block has-text-centered mt-0">
              <small
                >Ao clicar em cadastrar, você concorda com os termos de
                uso.</small
              >
            </div>
            <div class="block has-text-centered">
              <p>
                Já possui uma conta?
                <NuxtLink to="/cadastro/entrar">Clique aqui</NuxtLink>.
              </p>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  layout: 'cadastro/cadastroPrincipal',
  data() {
    return {}
  },
  methods: {
    cadastrarUsuario: (event) => {
      alert('alo goiania!')
    },
  },
}
</script>
<style>
body {
  background-color: #15364f;
}
small {
  font-size: 12px;
}
</style>>