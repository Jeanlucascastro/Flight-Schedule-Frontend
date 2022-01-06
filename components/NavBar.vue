<template>

<div>
  <b-navbar toggleable="lg" type="light" variant="light">
    <b-navbar-brand NuxtLink to="/" href="#">Flight Schedule</b-navbar-brand>

    <b-navbar-toggle target="nav-collapse"></b-navbar-toggle>

    <b-collapse id="nav-collapse" is-nav>
      <b-navbar-nav>
        <b-nav-item NuxtLink to="/cadastro" href="#">Cadastrar Voo</b-nav-item>
        <b-nav-item href="#">Calendario</b-nav-item>
      </b-navbar-nav>

      <!-- Right aligned nav items -->
      <b-navbar-nav class="ml-auto">
        <b-nav-form>
          <b-form-input size="sm" class="mr-sm-2" placeholder="Procurar agendamento"></b-form-input>
          <b-button size="sm" class="my-2 my-sm-0" type="submit">Procurar</b-button>
        </b-nav-form>


        <b-nav-item-dropdown right>
          <!-- Using 'button-content' slot -->
          <template #button-content>
            <em>Conta</em>
          </template>
          <b-dropdown-item to="/efetuarLogin" href="#">Login</b-dropdown-item>
          <b-dropdown-item href="#">Sair</b-dropdown-item>
        </b-nav-item-dropdown>
      </b-navbar-nav>
    </b-collapse>
  </b-navbar>
</div>


</template>



<script>
export default {
  name: 'NavBar'
}
</script>