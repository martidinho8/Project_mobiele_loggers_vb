<template>
  <v-app>
    <v-app-bar
      app
      color="secondary"
      dark
    >
      <div class="d-flex align-center">
        <v-img
          alt="Vitens Logo"
          class="shrink mr-2"
          contain
          src="../images/vitens_laatwatervoorjewerken.png"
          transition="scale-transition"
          width="125"
        />
        <router-link to="/"> 
                <v-btn
                  
                    class="mx-4"
                    icon
                  >   <v-icon size="24px">
                      mdi-home
                    </v-icon> </v-btn>
        </router-link> 

        <router-link to="/About"> 
            <v-btn
            
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
        ],
    }
  },
};
</script>

   