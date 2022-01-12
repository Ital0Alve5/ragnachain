<template>
  <div class="fullscreen bg-black text-white text-center q-pa-md flex flex-center">
    <div>
      <div style="font-size: 30vh">
        404
      </div>

      <div class="text-" style="opacity:.4">
       Erro, volte para a página anterior...
      </div>

      <q-btn
        class="q-mt-xl"
        color="white"
        text-color="black"
        unelevated
        to="/"
        label="Voltar"
        no-caps
      />
    </div>
  </div>
</template>

<script>
import { defineComponent } from 'vue'

export default defineComponent({
  name: 'Error404'
})
</script>
