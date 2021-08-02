<template>
  <v-form v-model="valid">
    <v-container  
    align="center">
    
    <v-row>
        <v-col
          cols="12"
          md="3"
         
        >

        <v-select :items="locations" required label="locatie" >

      </v-select>
          
        </v-col>

        <v-col
          cols="12"
          md="3"
        >
          <v-select :items="[1,2]" required label="Mobiele logger nummer" >

      </v-select>
        </v-col>

      </v-row>

  
     
      <v-row>
        <v-col
          cols="12"
          md="3"
         
        >
          <v-text-field
            v-model="name1"
            :rules="nameRules"
            label="Grootheid"
            required
          ></v-text-field>
        </v-col>

        <v-col
          cols="12"
          md="3"
        >
          <v-text-field
            v-model="name2"
            :rules="nameRules"

            label="Eenheid"
            required
          ></v-text-field>
        </v-col>

      </v-row>

            <v-row>
        <v-col
          cols="12"
          md="3"
         
        >
          <v-text-field
            v-model="name3"
            :rules="nameRules"
            label="Minimum"
            required
          ></v-text-field>
        </v-col>

        <v-col
          cols="12"
          md="3"
        >
          <v-text-field
            v-model="name4"
            :rules="nameRules"

            label="Maximum"
            required
          ></v-text-field>
        </v-col>

        

      </v-row>
           
             <v-btn
      depressed
      color="primary"
       cols="32"
          md="36"
    >
      Primary
    </v-btn>
    
    </v-container>
    <vuegraph />
  </v-form>
  
</template>

<script>

import vuegraph from './vuegraph'


  export default {
    components: {
      vuegraph
    },
    data () {
      return { 
      valid: false,
      name1: '',
      name2: '',
      nameRules: [
        v => !!v || 'Input is benodigd',
      ],
      locations: ['Tuul en Waal', 'Witharen', 'Spangenburg'],
      }
    }
  }
</script>
