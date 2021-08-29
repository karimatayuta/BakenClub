<template>
  
  <v-container>  

    <v-card 
      class="mx-auto blue-grey darken-4 pa-1" 
      outlined
      dense
    >

      <div class="text-left">
        <span class="font-weight-bold pa-1 blue-grey--text">preview</span>
      </div>

      <v-card-text 
        class="font-weight-bold pa-0 white--text" 
        style="white-space: pre-wrap;"
      >{{ create_data }}
      </v-card-text>

    </v-card>

    <v-container class="text-center">
      <a 
        href="https://twitter.com/share?ref_src=twsrc%5Etfw"
        class="twitter-share-button"
        data-show-count="false"
        data-size="large"
        data-hashtags="Demo"
        :data-text="create_data"
      >Tweet</a>
      <script async src="https://platform.twitter.com/widgets.js" charset="utf-8"></script>
    </v-container>



  </v-container>


</template>


<script>
export default {
  props: [
    "input_race_place", 
    "input_race_num",
    "input_race_bet_way",
    "input_race_bet_kind",
  ],

  data() {
    return {
      preps_race_place: this.input_race_place,
      preps_race_num: this.input_race_num,
      preps_race_bet_kind: this.input_race_bet_kind,
      preps_race_bet_way: this.input_race_bet_way,
      // button_text: "Create URL",
      button_text: "Create Text",
      create_data: "\n"+
        this.input_race_place+" "+
        this.input_race_num+"R\n"+
        this.input_race_bet_kind+"（"+
        this.input_race_bet_way+"）",
      fetch_data: [],

    }
  },
  methods: {
    onCopy(msg) {
      navigator.clipboard.writeText(msg)

      // alert(msg)
    }
  },
  // async fetch() {
  //   this.fetch_data = await fetch(
  //     'https://weather.tsukumijima.net/api/forecast/city/400040'
  //   ).then(res => res.json())
    
    // alert(this.fetch_data.title)
    // console.log(this.fetch_data)
}
</script>
