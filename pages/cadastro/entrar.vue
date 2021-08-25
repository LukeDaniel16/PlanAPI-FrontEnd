<template>
  <section class="section has-background-primary tamanho-login">
    <div class="container">
      <div class="columns is-mobile is-centered">
        <div class="column is-4">
          <div class="box">
            <div class="columns is-mobile is-centered">
              <div class="column is-7">
                <b-image
                  :src="require('@/assets/images/logoPLan1.png')"
                  alt="Plan logo"
                ></b-image>
              </div>
            </div>
            <b-field label="E-mail" label-position="inside">
              <b-input
                placeholder="joao.barro@gmail.com"
                v-model="login"
                type="email"
                maxlength="60"
                icon="envelope"
              ></b-input>
            </b-field>
            <b-field label="Senha" label-position="inside">
              <b-input
                v-model="senha"
                type="password"
                maxlength="30"
                icon="key"
              ></b-input>
            </b-field>
            <div class="block has-text-centered">
              <b-button
                type="is-primary is-outlined"
                expanded
                icon-right="user"
                v-on:click="loginUsuario"
                ><strong>Entrar</strong></b-button
              >
            </div>
            <div class="block has-text-centered">
              <p>
                Não possui uma conta?
                <NuxtLink to="/cadastro/cadastrar">Clique aqui</NuxtLink> e
                cadastre-se!
              </p>
            </div>
            <div class="block has-text-centered">
              <NuxtLink to="/">Voltar ao início</NuxtLink>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script>
import axios from 'axios'

export default {
  layout: 'cadastro/cadastroPrincipal',
  data() {
    return {
      senha: '',
      login: '',
    }
  },
  methods: {
    async loginUsuario() {
      let loginObject = {
        Email: this.login,
        Senha: this.senha,
      }

      try {
        const data = await this.$axios.$post(
          'https://localhost:44309/api/usuarios/login',
          loginObject
        )

        localStorage.setItem('IdUsuarioLogado', data)
        this.mensssageSucess('Logado com Sucesso')
        this.$router.push('/task/paraMim')
        console.log(data)
      } catch (error) {
        mensssageError('Erro ao fazer login')
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
}
</script>
<style>
.tamanho-login {
  min-height: 100vh;
}
</style>