<template>
  <section>
    <div class="box" v-for="item in datasTeste" :key="item.id">
      <div class="notification" >
        <div class="content">
          <p>{{ item.nome }}</p>
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
    }
  },
  created() {
    let teste = {
      id: 1,
      nome: 'AaAAAAa',
    }

    let teste2 = {
      id: 2,
      nome: 'BBBBB',
    }
    this.datasTeste.push(teste)
    this.datasTeste.push(teste2)

    console.log(this.datasTeste)
  },
}
</script>

<style>
</style>