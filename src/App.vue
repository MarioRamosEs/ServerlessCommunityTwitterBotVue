<template>
  <v-app>
    <v-app-bar>
      <v-container class="d-flex align-center py-0">
        <v-app-bar-title class="pl-0">
          <div class="d-flex align-center">
            <v-avatar
              rounded="0"
              class="mr-3"
              image="ServerlessTwitterBotLogo.png"
            />

            Serverless Twitter Bot
          </div>
        </v-app-bar-title>
        <v-spacer></v-spacer>
        <v-btn
          icon="mdi-twitter"
          color="whitesmoke"
          href="https://twitter.com/GigachadBot_"
          target="_blank"
        ></v-btn>
        <!--        <v-btn :icon="true" @click="toggleTheme"><v-icon>mdi-theme-light-dark</v-icon></v-btn>-->
      </v-container>
    </v-app-bar>

    <v-main>
      <section id="hero">
        <v-sheet class="d-flex align-center pb-16" color="grey-darken-3">
          <v-container class="text-center">
            <v-responsive class="mx-auto" width="600">
              <v-img src="/ServerlessTwitterBotLogo.png"></v-img>

              <h3 class="text-h3">Serverless Twitter Bot</h3>

              <!--              <p class="mt-4 text-medium-emphasis">
                This is a basic Vuetify 3 application designed to help get your feet wet with the next version of the framework. Visit our <a href="https://next.vuetifyjs.com/" target="_blank" rel="noopener noreferrer">documentation</a> for more information.
              </p>-->

              <p class="mt-4 text-medium-emphasis">
                This is a serverless Twitter bot that tweets a random sentence
                from a list of sentences
              </p>
              <p class="mt-4 text-medium-emphasis">
                Hosted in Azure using Functions, CosmosDB, KeyVault and Vue
              </p>
            </v-responsive>
          </v-container>
        </v-sheet>
      </section>

      <v-sheet class="py-16">
        <section id="filter">
          <NewSentenceComponent />
        </section>

        <v-container>
          <v-divider class="my-12" />
        </v-container>

        <section id="github">
          <SourceCodeComponent />
        </section>
      </v-sheet>
    </v-main>

    <v-footer>
      <v-container
        class="text-overline d-flex align-center justify-space-between"
      >
        <div>
          <a href="https://marioramos.es" target="_blank"
            >Copyright &copy; 2022 Mario Ramos</a
          >
        </div>
        <div>
          Made with
          <v-btn
            variant="text"
            href="https://next.vuetifyjs.com/"
            target="_blank"
            icon="mdi-vuetify"
            color="whitesmoke"
          >
          </v-btn>
        </div>
      </v-container>
    </v-footer>
  </v-app>
</template>

<script>
//import { useTheme} from "vuetify";
import NewSentenceComponent from "./components/NewSentenceComponent.vue";
import SourceCodeComponent from "./components/SourceCodeComponent.vue";

export default {
  name: "App",
  components: { SourceCodeComponent, NewSentenceComponent },
  /*    setup() {
      const theme = useTheme()
      return {
        theme,
        toggleTheme: () => theme.global.name.value = theme.global.current.value.dark ? 'light' : 'dark'
      }
    }*/
};
</script>

<style>
a {
  color: whitesmoke;
  text-decoration: none; /* no underline */
}
</style>
