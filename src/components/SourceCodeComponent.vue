<template>
  <v-container>
    <v-row justify="space-between">
      <v-col cols="auto">
        <v-responsive width="550">
          <h2 class="text-h4">Take a look at the code</h2>

          <strong class="mt-3"> Don't be shy, you can contribute! </strong>

          <p class="mt-8">
            The backend consists of a set of Azure Functions, in a solution
            using Clean Architecture, CQRS and MediatR
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
            href="https://github.com/MarioRamosEs/ServerlessCommunityTwitterBotVue"
            target="_blank"
          >
            FrontEnd Code
          </v-btn>

          <p class="mt-8">
            You can check a technical post about the project here
          </p>
          <v-btn
            class="mt-2"
            prepend-icon="mdi-file-document"
            href="https://marioramos.es/serverless-community-twitter-bot/"
            target="_blank"
          >
            Technical Post
          </v-btn>
        </v-responsive>
      </v-col>

      <v-img max-width="400" max-height="300" src="Octocat.png" />
    </v-row>
  </v-container>
</template>
<script>
export default {
  name: "SourceCodeComponent",
};
</script>
