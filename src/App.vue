<template>
  <v-app>
    <v-app-bar>
      <v-container class="d-flex align-center py-0">
        <v-app-bar-title class="pl-0">
          <div class="d-flex align-center">
            <v-avatar
              rounded="0"
              class="mr-3"
              image="https://cdn.vuetifyjs.com/docs/images/logos/v.png"
            />

            Vuetify 3
          </div>
        </v-app-bar-title>
<!--        <v-spacer></v-spacer>
        <v-btn :icon="true" @click="toggleTheme"><v-icon>mdi-theme-light-dark</v-icon></v-btn>-->
      </v-container>
    </v-app-bar>

    <v-main>
      <section id="hero">
        <v-sheet
          class="d-flex align-center pb-16"
          color="grey-darken-3"
        >
          <v-container class="text-center">
            <v-responsive class="mx-auto" width="500">
              <v-img src="https://cdn.vuetifyjs.com/docs/images/logos/v.png"></v-img>

              <h3 class="text-h3">
                Try the new Vuetify
              </h3>

              <p class="mt-4 text-medium-emphasis">
                This is a basic Vuetify 3 application designed to help get your feet wet with the next version of the framework. Visit our <a href="https://next.vuetifyjs.com/" target="_blank" rel="noopener noreferrer">documentation</a> for more information.
              </p>
            </v-responsive>
          </v-container>
        </v-sheet>
      </section>

      <v-sheet class="py-16">
        <section id="filter">
          <v-container>
            <v-row justify="space-between">
              <v-col cols="auto">
                <v-responsive width="350">
                  <h2 class="text-h4">
                    New customization system
                  </h2>

                  <p class="text-success mt-3">
                    Global Defaults
                  </p>

                  <strong class="mt-3">
                    Version 3 Only
                  </strong>

                  <p class="mt-8">
                    Vuetify 3 has an unprecedented level of customization options that make implementing any design system easy.
                  </p>

                  <p class="mt-8">
                    Assign default values for all components in the library, including nested support.
                  </p>

                  <v-btn
                    class="mt-6"
                    href="https://next.vuetifyjs.com/features/global-configuration/"
                    target="_blank"
                    rel="noopener noreferrer"
                  >
                    More Information
                  </v-btn>
                </v-responsive>
              </v-col>

              <v-img
                max-width="400"
                src="https://cdn.vuetifyjs.com/store/themes/vite-free/chips-bar.png"
              />
            </v-row>
          </v-container>
        </section>

<!--        <v-container>
          <v-divider class="my-12" />
        </v-container>-->

      </v-sheet>


    </v-main>

    <v-footer>
      <v-container class="text-overline d-flex align-center justify-space-between">
        <div>
          <a href="https://marioramos.es" target="_blank" >Copyright &copy; 2022 Mario Ramos</a>
        </div>
        <div>
          Made with
          <v-btn variant="text" href="https://next.vuetifyjs.com/" target="_blank" icon="mdi-vuetify" size="x-large" color="white">
          </v-btn>
        </div>
      </v-container>
    </v-footer>
  </v-app>
</template>

<script>
  //import { useTheme} from "vuetify";
  export default {
    name: 'App',
/*    setup() {
      const theme = useTheme()
      return {
        theme,
        toggleTheme: () => theme.global.name.value = theme.global.current.value.dark ? 'light' : 'dark'
      }
    }*/
  }
</script>

<style>
a {
  color: whitesmoke;
  text-decoration: none; /* no underline */
}
</style>
