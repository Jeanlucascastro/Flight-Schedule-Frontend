<template>
<div>
<div class="container">
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
          nome: '',
          initd: '',
          finald: '',
          fli: 2332,
        },
        foods: [{ text: 'Selecione um', value: null }, '2323', 'King Air ', 'Phanon', 'Seneca'],
        show: true
      }
    },
    methods: {
      onSubmit(event) {
        event.preventDefault()
        alert(JSON.stringify(this.form))
                axios ({
      method: "post",
      url: "http://localhost:8080/flights/",
      data: this.form.JSON,
      headers: {"Content-Type": "application/json"  },}).then(function (response){
          console.log(response);
      }).catch(function (response){
          console.log(response);
      });
        //dataSend = (JSON.stringify(this.form))
      },

      onReset(event) {
        event.preventDefault()
        // Reset our form values
        this.form.nome = ''
        this.form.initd = ''
         this.form.finald = ''
        this.form.fli = null
        

        // Trick to reset/clear native browser form validation state
        this.show = false
        this.$nextTick(() => {
          this.show = false
        })
      }
    }

  }
 


  
</script>