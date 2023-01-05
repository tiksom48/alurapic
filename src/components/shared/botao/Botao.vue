<template>
  <div :class="estiloDoBotao">
    <button @click="disparaAcao()" class="botao" :type="tipo">{{ rotulo }}</button>
  </div>
</template>

<script>
export default {
  props: {
    tipo: {
      type: String,
      required: true,
    },

    rotulo: {
      type: String,
      required: true,
    },

    confirmacao: Boolean,
    estilo: String,
  },

  methods: {
    disparaAcao() {
      console.log(typeof this.confirmacao);
      if (this.confirmacao) {
        if (confirm("Confirma operacao?")) {
          this.$emit("botaoAtivado");
        }
        return;
      }
      this.$emit("botaoAtivado");
    },
  },

  computed: {
    
   // eslint-disable-next-line 
    estiloDoBotao() {
      // se o valor é padrão ou não passou nada para estilo
      if (this.estilo == "botao-padrao") return "botao botao-padrao";
      if (this.estilo == "botao-perigo") return "botao botao-perigo";
    },
  },
};
</script>

<style>
.botao {
  display: inline-block;
  padding: 10px;
  border-radius: 3px;
  margin: 10px;
  font-size: 1.2em;
}
.botao-perigo {
  background: firebrick;
  color: white;
}
.botao-padrao {
  background: darkcyan;
  color: white;
}
</style>
