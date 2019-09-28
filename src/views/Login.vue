<template>
<div>

  <template>
    <mdb-container class="mt-4 z-depth-3 py-3">
      <mdb-row class="justify-content-md-center">
        <mdb-col col="2"></mdb-col>
        <mdb-col col="12" md="8" class="bg-white text-dark py-4 rounded">
            
            <div>
              <img src="@/assets/logo.png" alt="Logo del aplicativo" class="img-fluid mx-auto my-2 d-block" id="img-logo">
              <h1 class="text">Diario</h1>
            </div>
            
            <div>
              <form class="md-form" @submit.prevent>
                <div class="text-secondary text-left">
                  <mdb-input v-model="mail" type="email" class="w-75 mx-auto" label="Email" icon="envelope"/>
                  <mdb-input v-model="password" type="password" class="w-75 mx-auto" label="Password" icon="lock"/>
                </div>
                <div class="text-center">
                  <mdb-btn @click="registro" class="w-75 mx-auto" dark color="indigo">Entrar</mdb-btn>
                </div>
                <hr class="w-75 mx-auto gba-stylish-strong">
                <div>
                  <mdb-row class="w-75 mx-auto">
                    <mdb-col col="12" md="6">
                      <mdb-btn @click="facebook" outline="primary" class="w-100">Facebook</mdb-btn>
                    </mdb-col>
                    <mdb-col col="12" md="6">
                      <mdb-btn @click="google" outline="primary" class="w-100">Google</mdb-btn>
                    </mdb-col>
                  </mdb-row>
                </div>

              </form>
            </div>

        </mdb-col>
        <mdb-col col="2"></mdb-col>
      </mdb-row>

    </mdb-container>
  </template>
  
</div>
</template>

<script>
import {mdbContainer, mdbRow, mdbCol} from 'mdbvue';
import { mdbInput, mdbBtn } from 'mdbvue';
export default {
    name : 'Login',
    components: {
      mdbContainer,
      mdbRow,
      mdbCol,
      mdbInput,
      mdbBtn
    },
    data() {
      return {
        estado: false,
        mail : '',
        password : ''
      }
    },
    methods: {
      google(){
        console.log('Google');
      },
      facebook(){
        console.log('facebook');
      },
      registro(){
        console.log('Registro por manual');
      }
    },
}
</script>

<style scoped>
  @import url('https://fonts.googleapis.com/css?family=Lexend+Deca&display=swap');
  h1{
    font-family: 'Lexend Deca', sans-serif;
  }

  .text {
    text-transform: uppercase;
    background: linear-gradient(to right, #30CFD0 0%, #330867 100%);
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent; 
  }

  #img-logo{
      width:8em;
  }

</style>