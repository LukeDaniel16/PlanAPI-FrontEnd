<template>
  <section class="section is-medium">
    <div class="container">
      <div class="columns is-mobile is-centered">
        <div class="column is-4">
          <div class="box">
            <b-image
              :src="require('@/assets/images/logoPLan1.png')"
              alt="PLan logo"
              ratio="square"
            ></b-image>
            <b-field label="Nome" label-position="inside">
              <b-input
                placeholder="Ex: João de Barro"
                maxlength="160"
              ></b-input>
            </b-field>
            <b-field label="Apelido" label-position="inside">
              <b-input placeholder="Joaozinho" maxlength="120"></b-input>
            </b-field>
            <b-field label="E-mail" label-position="inside">
              <b-input
                placeholder="joao.barro@gmail.com"
                type="email"
                maxlength="60"
              ></b-input>
            </b-field>
            <b-field label="Senha" label-position="inside">
              <b-input type="password" maxlength="30"></b-input>
            </b-field>
            <div class="block has-text-centered">
              <b-button type="is-primary is-outlined" expanded
                ><strong>Cadastrar!</strong></b-button
              >
            </div>
            <div class="block has-text-centered">
              <p>
                Já possui uma conta? Clique
                <NuxtLink to="/cadastro/entrar">aqui</NuxtLink>.
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
}
</script>
<style>
body {
  background-color: #15364f;
}
</style>>