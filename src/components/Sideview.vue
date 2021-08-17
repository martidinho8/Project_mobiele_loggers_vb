<template>
  <v-form v-model="valid">
    <v-container align="center">
      <v-row>
        <v-col>
          <v-select :items="locations" required label="locatie"> </v-select>
        </v-col>

        <v-col>
          <v-select :items="[1, 2]" required label="Mobiele logger nummer">
          </v-select>
        </v-col>
      </v-row>

      <v-row>
        <v-col>
          <v-text-field
            v-model="name1"
            :rules="nameRules"
            label="Grootheid"
            required
          ></v-text-field>
        </v-col>

        <v-col>
          <v-text-field
            v-model="name2"
            :rules="nameRules"
            label="Eenheid"
            required
          ></v-text-field>
        </v-col>
      </v-row>

      <v-row>
        <v-col>
          <v-text-field
            v-model="name3"
            :rules="nameRules"
            label="Minimum"
            required
          ></v-text-field>
        </v-col>

        <v-col>
          <v-text-field
            v-model="name4"
            :rules="nameRules"
            label="Maximum"
            required
          ></v-text-field>
        </v-col>
      </v-row>
          <div align="center">
      <v-btn
        depressed
        color="primary"
        align="center"
        v-on:click="Parameter = false"
      >
        Fetch data
      </v-btn>
    </div>
    </v-container>



    <div class="small" v-if="!Parameter">
      <vuegraph />

      <!-- <vuechart  /> -->
    </div>
  </v-form>
</template>

<script>
import vuegraph from "./vuegraph";

export default {
  components: {
    vuegraph,
  },
  data() {
    return {
      Parameter: true,
      valid: false,
      name1: "",
      name2: "",
      name3: "",
      name4: "",
      nameRules: [(v) => !!v || "Input is benodigd"],
      locations: ["Tuul en Waal", "Witharen", "Spangenburg"],
    };
  },
};
</script>

<style>
.small {
  max-width: 1200px;
  margin: 150px auto;
}
</style>