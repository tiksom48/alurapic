<template>
  <div>
<h1>{{ titulo }}</h1>

<ul>

<li v-for="foto of fotos">
  <img :src="foto.url" :alt="foto.titulo">
</li>

</ul>

  </div>
</template>

<script>

export default {

  data() {

    return {

      titulo: 'AluraPic',
      fotos: [
      {
        url: 'https://fotografiamais.com.br/wp-content/uploads/2018/09/fotos-de-cachorro-existe-mercado.jpg',
        titulo: 'cachorro'
      },
      {
        url: 'https://fotografiamais.com.br/wp-content/uploads/2018/09/fotos-de-cachorro-existe-mercado.jpg',
        titulo: 'cachorrão'
      }
    ]
    }
  }
}
</script>

<style>

</style>
