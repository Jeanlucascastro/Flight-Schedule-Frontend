<template>
<div>
  <NavBar/>
  <Formulario/>
  <Footer/>
    
    </div>

</template>


<script lang="ts">
import Vue from 'vue'
import Formulario from '~/components/Formulario.vue'

export default Vue.extend({
  components: { Formulario },
  // name: 'IndexPage',
  layout: 'cadastro',
})
</script>