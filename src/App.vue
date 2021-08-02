<template>
  <v-app>
    <v-app-bar
      app
      color="secondary"
      dark
    >
      <div class="d-flex align-center">
        <v-img
          alt="Vuetify Logo"
          class="shrink mr-2"
          contain
          src="https://cdn.vuetifyjs.com/images/logos/vuetify-logo-dark.png"
          transition="scale-transition"
          width="40"
        />
        <v-img
          alt="Vuetify Name"
          class="shrink mt-1 hidden-sm-and-down"
          contain
          min-width="100"
          src="https://cdn.vuetifyjs.com/images/logos/vuetify-name-dark.png"
          width="100"
        />
        <router-link to="/"> 
                <v-btn
                    :key="mdi-home"
                    class="mx-4"
                    icon
                  >   <v-icon size="24px">
                      mdi-home
                    </v-icon> </v-btn>
        </router-link> 

        <router-link to="/About"> 
            <v-btn
            :key="mdi-email"
            class="mx-4"
            icon
          >   <v-icon size="24px">
              mdi-email
            </v-icon> </v-btn>
        </router-link> 
      </div>

      <v-spacer></v-spacer>

      <v-btn
        href="https://github.com/martidinho8/Project_mobiele_loggers_vb.git"
        target="_blank"
        text
      >
        <span class="mr-2">Latest Release</span>
        <v-icon>mdi-open-in-new</v-icon>
      </v-btn>
    </v-app-bar>

    <v-main>
      
      <router-view/>
    </v-main>
  </v-app>
</template>

<script>

export default {
  name: 'App',

data () {
    return {
        icons: [
          'mdi-home',
          'mdi-email',
        ]
    }
  },
};
</script>

   