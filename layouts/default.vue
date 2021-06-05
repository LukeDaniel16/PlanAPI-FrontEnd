<template>
  <div>
    <b-navbar>
      <template #brand>
        <b-navbar-item tag="router-link" :to="{ path: '/' }">
          <p>Find my <i>tasks!</i></p>
        </b-navbar-item>
      </template>
      <template #start>
        <b-navbar-item tag="nuxt-link" to="/">Principal</b-navbar-item>
        <b-navbar-item tag="nuxt-link" to="cadastro/login"
          >Informações</b-navbar-item
        >
        <b-navbar-item tag="nuxt-link" to="/login">Sobre nós</b-navbar-item>
      </template>
      <template #end>
        <b-navbar-item tag="div">
          <div class="buttons">
            <button class="button is-info is-outlined is-rounded">
              <strong>Cadastre-se</strong>
            </button>
            <button class="button is-info is-outlined is-rounded">
              Entrar
            </button>
          </div>
        </b-navbar-item>
      </template>
    </b-navbar>
    <Nuxt />
  </div>
</template>

<script>
export default {}
</script>
<style scoped>
p {
  color: #023e8a;
}
.is-link {
  color: #023e8a;
}
</style>