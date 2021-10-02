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
                  <v-card elevation="1" shaped rounded class="ma-5" tile>
                      <v-card-title class="pl-2 pa-0" style="color:#969696;font-size:10px">Vivo IPL</v-card-title>
                      <v-divider></v-divider>
                      <v-card-text>
                          <v-row >
                              <v-col class="pl-0 ml-0 flag-left" cols="12" sm="2" ><v-img contain max-height="40" max-width="40" src="https://d13ir53smqqeyp.cloudfront.net/flags/cr-flags/KKR-CR1@2x.png"></v-img></v-col>
                              <v-col  cols="12" sm="8" class="flex text-center" >1.2</v-col>
                              <v-col class="flag-rigth" cols="12" sm="2" >MI</v-col>
                          </v-row>
                      </v-card-text>
                  </v-card>
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
export default {
  data: () => ({
    links: ["Dashboard", "Messages", "Profile", "Updates"],
  }),
};
</script>

<style >
.flag-left{
    user-select: none;
    font-family: NoWay;
    font-weight: 400;
    color: inherit;
    box-sizing: border-box;
    -webkit-tap-highlight-color: transparent;
    display: flex;
    align-items: center;
    justify-content: flex-end;
    border-top-right-radius: 20px;
    border-bottom-right-radius: 20px;
    background-color: rgb(158, 146, 175);
}
.flag-rigth{
    user-select: none;
    font-family: NoWay;
    font-weight: 400;
    color: inherit;
    box-sizing: border-box;
    -webkit-tap-highlight-color: transparent;
    display: flex;
    align-items: center;
    justify-content: flex-start;
    border-top-left-radius: 20px;
    border-bottom-left-radius: 20px;
    background-color: rgb(158, 146, 175);
}
</style>