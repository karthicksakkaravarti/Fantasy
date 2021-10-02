<template>
  <v-card elevation="1" shaped rounded class="ma-5" tile>
    <v-card-title class="pl-2 pa-0" style="color: #969696; font-size: 10px"
      >Vivo IPL</v-card-title
    >
    <v-divider></v-divider>
    <v-card-text class="pt-1 pb-1 pa-0">
      <v-row class="ma-0 pa-0">
        <v-col cols="12" sm="2">
          <v-img
            contain
            max-height="70"
            max-width="70"
            src="https://d13ir53smqqeyp.cloudfront.net/flags/cr-flags/MI-CR3@2x.png"
          ></v-img>
        </v-col>
        <v-col cols="12" class="mt-5" sm="1">
          <b>MI</b>
        </v-col>

        <v-col
          cols="12"
          sm="6"
          class="mt-5 text-center red--text"
          >{{ timeLeft }} left</v-col
        >
        <v-col class="mt-5" cols="12" sm="1">
          <b>DC</b>
        </v-col>

        <v-col cols="12" sm="2">
          <v-img
            contain
            max-height="70"
            max-width="70"
            src="https://d13ir53smqqeyp.cloudfront.net/flags/cr-flags/DC-CR3@2x.png"
          ></v-img>
        </v-col>
      </v-row>
    </v-card-text>
  </v-card>
</template>

<script>
export default {
  props: {
    hours: {
      default: 0,
    },

    minutes: {
      default: 0,
    },

    seconds: {
      default: 0,
    },

    endpoint: {},
  },

  data() {
    return {
      hoursLeft: this.hours,
      minutesLeft: this.minutes,
      secondsLeft: this.seconds,
    };
  },

  methods: {
    resetTimer() {
      this.hoursLeft = this.hours;
      this.minutesLeft = this.minutes;
      this.secondsLeft = this.seconds;
    },

    zeroPad(input, length) {
      return (Array(length + 1).join("0") + input).slice(-length);
    },
  },

  mounted() {
    this.resetTimer();

    this.$nextTick(function () {
      window.setInterval(() => {
        if (this.secondsLeft > 0) {
          this.secondsLeft--;
        } else if (this.secondsLeft == 0 && this.minutesLeft > 0) {
          this.secondsLeft = 59;
          this.minutesLeft--;
        } else if (
          this.secondsLeft == 0 &&
          this.minutesLeft == 0 &&
          this.hoursLeft > 0
        ) {
          this.secondsLeft = 59;
          this.minutesLeft = 59;
          this.hoursLeft--;
        } else {
          // Timer hits 0 do what you want to do here.
        }
      }, 1000);
    });
  },
  computed: {
    timeLeft: function () {
      if (this.hours !== 0) {
        return (
          this.hoursLeft +
          ":" +
          this.zeroPad(this.minutesLeft, 2) +
          ":" +
          this.zeroPad(this.secondsLeft, 2)
        );
      } else if (this.minutes !== 0) {
        return this.minutesLeft + ":" + this.zeroPad(this.secondsLeft, 2);
      } else {
        return this.secondsLeft;
      }
    },
  },
};
</script>

<style>
.flag-left {
  /* display: flex;  
    justify-content: flex-end; */
  border-top-right-radius: 20px;
  border-bottom-right-radius: 20px;
  background-color: rgb(158, 146, 175);
}
.flag-rigth {
  display: flex;
  align-items: center;
  justify-content: flex-start;
  border-top-left-radius: 20px;
  border-bottom-left-radius: 20px;
  background-color: rgb(158, 146, 175);
}
</style>