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

          <v-form v-model="valid" class="mt-6">
            <v-textarea
              :loading="loading"
              label="Sentence"
              variant="outlined"
              counter
              :rules="rules"
              v-model="newSentence"
              rows="3"
              auto-grow
            ></v-textarea>

            <v-btn
              prepend-icon="mdi-send"
              :loading="loading"
              @click="sendSentence"
            >
              Send
            </v-btn>
          </v-form>

        </v-responsive>
      </v-col>

      <v-img max-width="400" max-height="300" src="gigachad.jpg" />
    </v-row>
  </v-container>

  <v-snackbar
    v-model="snackbar"
    color="primary"
    :timeout="2000"
  >
    {{ text }}
    <template v-slot:action="{ attrs }">
    </template>
  </v-snackbar>

</template>
<script>
export default {
  name: "NewSentenceComponent",
  data: () => ({
    rules: [(v) => v.length <= 280 || "Max 280 characters"],
    newSentence: "",
    loading: false,
    valid: false,
    snackbar: false,
    text: ''
  }),
  methods: {
    async sendSentence() {
      if (!this.valid || this.newSentence.length === 0) {
        return;
      }

      console.log('hey')
      this.loading = true;
      try {
        const response = await fetch(
          "https://communitytwitterbot.azurewebsites.net/api/CreatePendingSentence?code=KA4yB-TU9pZiggBY-pzXhBGICnvFnmSncwcJ9pGcsW0JAzFuPDoy9w==",
          {
            method: "POST",
            headers: {
              "Content-Type": "application/json",
            },
            body: JSON.stringify({ Text: this.newSentence }),
          }
        );
        this.text = "Your sentence has been sent to the bot!";
        this.snackbar = true;
      } catch (e) {
        console.error(e);
        this.text = "There was an error sending your sentence";
        this.snackbar = true;
      }
      this.loading = false;
    },
  },
};
</script>
