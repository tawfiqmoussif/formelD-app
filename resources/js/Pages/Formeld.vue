<template>
 
    <v-app>
  <v-stepper
    v-model="e6"
    vertical
  >
    <v-stepper-step
      :complete="e6 > 1"
      step="1"
    >
      Select an app
      <small>Summarize if needed</small>
    </v-stepper-step>

    <v-stepper-content step="1">
      
  <v-form v-model="valid">
    <v-container>
      <v-row>
        <v-col
          cols="12"
          md="4"
        >
          <v-text-field
            v-model="nDeProjet"
            :rules="nameRules"
            :counter="10"
            label="N de projet"
            required
          ></v-text-field>
        </v-col>
         <v-col
          cols="12"
          md="4"
        >
            <v-combobox
            :items="typesActivite"
            >

            </v-combobox>
        </v-col>
        <v-col
          cols="12"
          md="4"
        >
          <v-text-field
            v-model="lastname"
            :rules="nameRules"
            :counter="10"
            label="Last name"
            required
          ></v-text-field>
        </v-col>

        <v-col
          cols="12"
          md="4"
        >
          <v-text-field
            v-model="email"
            :rules="emailRules"
            label="E-mail"
            required
          ></v-text-field>
        </v-col>
      </v-row>
    </v-container>
  </v-form>

      <v-btn
        color="primary"
        @click="e6 = 2"
      >
        Continuee
      </v-btn>
      <v-btn text>
        Cancel
      </v-btn>
    </v-stepper-content>

    <v-stepper-step
      :complete="e6 > 2"
      step="2"
    >
      Configure analytics for this app
    </v-stepper-step>

    <v-stepper-content step="2">
      <v-card
        color="grey lighten-1"
        class="mb-12"
        height="200px"
      ></v-card>
      <v-btn
        color="primary"
        @click="e6 = 3"
      >
        Continue
      </v-btn>
      <v-btn text>
        Cancel
      </v-btn>
    </v-stepper-content>

    <v-stepper-step
      :complete="e6 > 3"
      step="3"
    >
      Select an ad format and name ad unit
    </v-stepper-step>

    <v-stepper-content step="3">
      <v-card
        color="grey lighten-1"
        class="mb-12"
        height="200px"
      ></v-card>
      <v-btn
        color="primary"
        @click="e6 = 4"
      >
        Continue
      </v-btn>
      <v-btn text>
        Cancel
      </v-btn>
    </v-stepper-content>

    <v-stepper-step step="4">
      View setup instructions
    </v-stepper-step>
    <v-stepper-content step="4">
      <v-card
        color="grey lighten-1"
        class="mb-12"
        height="200px"
      ></v-card>
      <v-btn
        color="primary"
        @click="e6 = 1"
      >
        Continue
      </v-btn>
      <v-btn text>
        Cancel
      </v-btn>
    </v-stepper-content>
  </v-stepper>
  </v-app>
</template>
<script>
  export default {
     data: () => ({
      
        e6: 1,
      
      valid: false,
      nDeProjet: '',
      lastname: '',
      nameRules: [
        v => !!v || 'la valeur est obligatoire',
        v => v.length <= 40 || 'La valeur doit comporter moins de 40 caractères',
      ],
      email: '',
      emailRules: [
        v => !!v || 'E-mail is required',
        v => /.+@.+/.test(v) || 'E-mail must be valid',
      ],
      typesActivite: [
          'C&R',
          'Operation de tri',
          'Controle de fonction',
          'Assistance SAP',
          'Projet exterieur',
          'Dommaqes dus au transport',
          'Test de bruit',
          'Autre',
        ],
    
    }),
  }
</script>