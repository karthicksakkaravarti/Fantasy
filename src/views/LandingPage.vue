<template>
  <v-app id="inspire">
    <v-app-bar app color="#c51d23" flat dense>
      <v-toolbar-title
        class="flex text-center"
        style="width: 300px; color: white"
        dark
      >
        <b>Fantasy</b>
      </v-toolbar-title>

      <v-btn
        v-if="$vuetify.breakpoint.smAndDown"
        rounded
        x-small
        outlined
        color="white"
        >Login</v-btn
      >
      <v-btn rounded v-else small outlined color="white">Login</v-btn>
    </v-app-bar>

    <v-main class="grey lighten-3">
      <v-container>
        <v-row>
          <v-col v-if="!$vuetify.breakpoint.smAndDown" cols="12" sm="2">
          </v-col>

          <v-col cols="12" sm="8">
            <v-sheet color="none" min-height="80vh" rounded="lg">
              <v-stepper elevation="0" flat>
                <v-stepper-header>
                  <v-stepper-step style="color:#969696;font-size:10px" step="1"> Select Match </v-stepper-step>

                  <v-divider></v-divider>

                  <v-stepper-step step="2" style="color:#969696;font-size:10px">
                    Create Fantasy Team
                  </v-stepper-step>

                  <v-divider></v-divider>

                  <v-stepper-step step="3" style="color:#969696;font-size:10px"> Jion Event </v-stepper-step>
                </v-stepper-header>
              </v-stepper>
              <v-divider></v-divider>
              <b class="ml-2" style="color:#969696;font-size:14px">Upcoming Matches</b>
              <v-row>
                <v-col>
                  <Match_Preview hours="1" minutes="0" seconds="0"/>
                </v-col>
              </v-row>
            </v-sheet>
          </v-col>

          <v-col v-if="!$vuetify.breakpoint.smAndDown" cols="12" sm="2">
          </v-col>
        </v-row>
      </v-container>
    </v-main>
  </v-app>
</template>

<script>
import Match_Preview from "../components/Match-Preview.vue";
export default {
  data: () => ({
    links: ["Dashboard", "Messages", "Profile", "Updates"],
  }),
  components: {
    Match_Preview
  },
};
</script>

