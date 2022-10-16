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
          <v-container>
            <v-row justify="space-between">
              <v-col cols="auto">
                <v-responsive width="550">
                  <h2 class="text-h4">Send a new sentence</h2>

                  <strong class="mt-3"> You are also part of this! </strong>

                  <p class="mt-8">
                    Submit your preferred phrase so that (after we validate it)
                    it becomes part of the bot's database
                  </p>

                  <v-textarea
                    :loading="loading"
                    class="mt-6"
                    label="Sentence"
                    variant="outlined"
                    counter
                    :rules="rules"
                    v-model="value"
                    rows="3"
                    auto-grow
                  ></v-textarea>

                  <v-btn prepend-icon="mdi-send" :loading="loading">
                    Send
                  </v-btn>
                </v-responsive>
              </v-col>

              <v-img max-width="400" max-height="300" src="gigachad.jpg" />
            </v-row>
          </v-container>
        </section>

        <v-container>
          <v-divider class="my-12" />
        </v-container>

        <section id="github">
          <v-container>
            <v-row justify="space-between">
              <v-col cols="auto">
                <v-responsive width="550">
                  <h2 class="text-h4">Take a look at the code</h2>

                  <strong class="mt-3">
                    Don't be shy, you can contribute!
                  </strong>

                  <p class="mt-8">
                    The backend consists of a set of Azure Functions, in a
                    solution using Clean Architecture, CQRS and MediatR
                  </p>

                  <v-btn
                    class="mt-2"
                    prepend-icon="mdi-server"
                    href="https://github.com/MarioRamosEs/ServerlessCommunityTwitterBot"
                    target="_blank"
                  >
                    BackEnd Code
                  </v-btn>

                  <p class="mt-8">
                    The frontend is a Vue 3 application, using Vuetify 3
                  </p>

                  <v-btn
                    class="mt-2"
                    prepend-icon="mdi-web"
                    href="https://github.com/MarioRamosEs/ServerlessCommunityTwitterBot"
                    target="_blank"
                  >
                    FrontEnd Code
                  </v-btn>
                </v-responsive>
              </v-col>

              <v-img max-width="400" max-height="300" src="Octocat.png" />
            </v-row>
          </v-container>
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
export default {
  name: "App",
  /*    setup() {
      const theme = useTheme()
      return {
        theme,
        toggleTheme: () => theme.global.name.value = theme.global.current.value.dark ? 'light' : 'dark'
      }
    }*/

  data: () => ({
    rules: [(v) => v.length <= 280 || "Max 280 characters"],
    value: "",
    loading: false,
  }),
};
</script>

<style>
a {
  color: whitesmoke;
  text-decoration: none; /* no underline */
}
</style>
