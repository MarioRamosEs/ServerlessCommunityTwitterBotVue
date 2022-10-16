<template>
  <v-container>
    <v-row justify="space-between">
      <v-col cols="auto">
        <v-responsive width="550">
          <h2 class="text-h4">Send a new sentence</h2>

          <strong class="mt-3"> You are also part of this! </strong>

          <p class="mt-8">
            Submit your preferred phrase so that (after we validate it) it
            becomes part of the bot's database
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

          <v-btn prepend-icon="mdi-send" :loading="loading"> Send </v-btn>
        </v-responsive>
      </v-col>

      <v-img max-width="400" max-height="300" src="gigachad.jpg" />
    </v-row>
  </v-container>
</template>
<script>
export default {
  name: "NewSentenceComponent",
  data: () => ({
    rules: [(v) => v.length <= 280 || "Max 280 characters"],
    value: "",
    loading: false,
  }),
};
</script>
