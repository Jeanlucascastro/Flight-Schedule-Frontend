<template>
<div>
<div class="mx-auto mt-5" style="width: 500px; height: 500px;" vertical-align="center">
  <b-form inline>
    <label class="sr-only" for="inline-form-input-name ">Name</label>
    <b-form-input
      id="inline-form-input-name"
      class="mb-2 mr-sm-2 mb-sm-0"
      placeholder="Usuario"
    ></b-form-input>

    <label class="sr-only" for="inline-form-input-username">Usuario</label>
    <b-input-group class="mb-2 mr-sm-2 mb-sm-0">
      <b-form-input id="inline-form-input-username" type="password" placeholder="Senha"></b-form-input>
    </b-input-group>

    <b-button variant="primary">Logar</b-button>

        <b-form-checkbox class="mb-2 mr-sm-2 mb-sm-0">Lembrar</b-form-checkbox>
  </b-form>
</div>




</div>
</template>



<script>
export default {
  name: 'Login'
}
</script>