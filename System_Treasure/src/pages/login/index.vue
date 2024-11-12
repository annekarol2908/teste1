<template>
    <v-sheet class="mx-auto" width="350">
      <v-form fast-fail @submit.prevent>
        <v-container class="flex-column">
            
        <v-text-field
          v-model="ID"
          :rules="idRules"
          label="ID de entrada"
          
        ></v-text-field>
  
        <v-text-field
          v-model="senha"
          :rules="senhaRules"
          label="Senha"
        ></v-text-field>
  
        <v-btn class="mt-2" type="submit" block>Entrar</v-btn>
        </v-container>
      </v-form>
    </v-sheet>
  </template>
  <script>
    export default {
      data: () => ({
        ID: '',
        idRules: [
          value => {
            if (value?.length >= 3) return true
  
            return 'Digite seu id para entrar.'
          },
        ],
        senha: '',
        senhaRules: [
          value => {
            if (/[^0-9]/.test(value)) return true
  
            return 'Digite sua senha para entrar.'
          },
        ],
      }),
    }
  </script>
  