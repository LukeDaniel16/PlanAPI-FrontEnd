<template>
  <div>
    <section class="hero is-danger is-fullheight">
      <div class="hero-body">
        <div class="">
          <p class="title">
            Ops!<br />
            Ocorreu um erro.
          </p>
          <div class="subtitle">
            <p>Procure nosso suporte para mais detalhes.</p>
            <br />
            <b-button tag="nuxt-link" to="/"
              >Voltar para página de início.</b-button
            >
          </div>
        </div>
      </div>
    </section>
  </div>
</template>

<script>
export default {
  layout: 'errorLayout',
}
</script>
<style scoped>
.hero-body {
  justify-content: center;
}
p {
  justify-content: center;
  text-align: center;
}
div .subtitle {
  justify-content: center;
  text-align: center;
}
</style>