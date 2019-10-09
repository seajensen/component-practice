<template>
    <v-container>
        <v-parallax src="https://res.cloudinary.com/twenty20/private_images/t_watermark-criss-cross-10/v1475125665000/photosp/e1d2ff68-b6a7-41da-a66b-bf3b670dee60/stock-photo-transportation-rain-raindrop-long-exposure-new-york-city-bokeh-vibrant-rainy-brooklyn-e1d2ff68-b6a7-41da-a66b-bf3b670dee60.jpg">
          <h1>This is {{userName}}'s component</h1>
          <v-form v-model="valid">
            <v-container>
              <v-text-field
                v-model="name"
                label="Username Here"
                :rules="nameRules"
                required
                ></v-text-field>
              <v-checkbox
                v-model="checkbox"
                :rules="[v => !!v || 'You must agree to continue!']"
                label="Do you agree the new Star Wars movies kind of suck?"
                required
              ></v-checkbox>
              <v-btn
                :disabled="!valid"
                color="success"
                class="mr-4"
                @click="changeUser()"
        >
            </v-container>
          </v-form>
        </v-parallax>
    </v-container>

</template>

<script>

export default {
  data: () => ({
    valid: false,
    userName: "Sean Jensen",
    nameRules: [
      function(val) {
        if(val == true) {
          return
        } else {
          return "Please enter your username"
        }
        if(val == "thor" || val == "Thor") {
          return "Please enter a different username"
        }
        if(val.length <= 10) {
          return
        } else {
          return "Username must be less than 10 characters"
        }
      }
    ]
  }),
  methods: {
    changeUser(val) {
      this.userName = val;
    }
  },
};
</script>

<style scoped>
h1 {
  font-family: Impact, Haettenschweiler, 'Arial Narrow Bold', sans-serif;
  color: white;
}
</style>