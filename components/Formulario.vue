<template>
<div>
<div class="container mt-5" style="width: 500px;">
    <b-form @submit="onSubmit" @reset="onReset" v-if="show">
      <b-form-group
        id="input-group-1"
        label="Nome:"
        label-for="input-1"
        description="Nome do aluno"
      >
        <b-form-input
          id="input-1"
          v-model="form.nome"
          type="Nome: "
          placeholder="Nome"
          required
        ></b-form-input>
      </b-form-group>

      <b-form-group id="input-group-2" label="Data Inicial:" label-for="input-2">
        <b-form-input
          id="input-2"
          v-model="form.initd"
          placeholder="Data Inicial"
          required
        ></b-form-input>
      </b-form-group>

            <b-form-group id="input-group-3" label="Data Final:" label-for="input-3">
        <b-form-input
          id="input-3"
          v-model="form.finald"
          placeholder="Data final "
          required
        ></b-form-input>
      </b-form-group>

      <b-form-group id="input-group-4" label="Avião:" label-for="input-4">
        <b-form-select
          id="input-4"
          v-model="form.fli"
          :options="foods"
          required
        ></b-form-select>
      </b-form-group>

      <b-button type="submit" variant="primary">Cadastrar</b-button>
      <b-button type="reset" variant="danger">Limpar</b-button>
    </b-form>
    <b-card class="mt-3" header="Form Data Result">
      <pre class="m-0">{{ form }}</pre>
    </b-card>
    </div>
  </div>





</template>



<script>
import axios from 'axios'

export default {
    data() {
      return {
        form: {
          nome: 'Joao',
          initd: 'PEdro',
          finald: 'Jose',
          fli: 2332,
        },
        foods: [{ text: 'Selecione um', value: null }, '2323', 'King Air ', 'Phanon', 'Seneca'],
        show: true
      }
    },



    methods: {
      onSubmit(event) {
        event.preventDefault()
      const enviar = this.form

      axios ({
      method: "post",
      url: "http://localhost:8080/flights/",
      data: enviar,
      headers: {"Content-Type": "application/json"  },}).then(function (response){
          console.log(response);
      }).catch(function (response){
          console.log(response);
      });

},

      onReset(event) {
        event.preventDefault()
        // Reset our form values
        this.form.nome = 'Jean '
        this.form.initd = '10 '
         this.form.finald = '10'
        this.form.fli = 2332
        

        // Trick to reset/clear native browser form validation state
        this.show = true
        this.$nextTick(() => {
          this.show = true
        })
      }
    }

  }
 


  
</script>