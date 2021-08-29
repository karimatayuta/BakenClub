<template>
  <div>
    
    <!-- baken_club -->

    <!-- <p class="text-justify"></p> -->
    <!-- 競馬場 -->
    <MainSelectButton 
      :subtitle="subtitle_race_place" 
      :dataset="dataset_race_place"
      @select_data="selected_race_place"
    ></MainSelectButton>

    <!-- レース番号 -->
    <MainSelectButton 
      :subtitle="subtitle_race_num" 
      :dataset="dataset_race_num"
      @select_data="selected_race_num"
    ></MainSelectButton>

    <!-- 馬券種類 -->
    <MainSelectButton
      :subtitle="subtitle_race_bet_kind"
      :dataset="dataset_race_bet_kind"
      @select_data="selected_race_bet_kind"
    ></MainSelectButton>

    <!-- 購入方法 -->
    <MainSelectButton
      :subtitle="subtitle_race_bet_way"
      :dataset="dataset_race_bet_way"
      @select_data="selected_race_bet_way"
    ></MainSelectButton>

    <!-- テーブルデータ -->
    <MainTableData></MainTableData>


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

  {{ input_race_place }}
  </div>

</template>

<script>
import MainSelectButton from '~/components/MainSelectButton.vue'
import MainTableData from '~/components/MainTableData.vue'
// import SampleButton from '~/components/SampleButton.vue'

export default {
  components: {
    MainSelectButton,
    MainTableData,
    // SampleButton,
  },
  data() {
    return {
      // サブタイトル
      subtitle_race_place: '競馬場',
      subtitle_race_num: 'レース番号',
      subtitle_race_bet_way: '購入方法',
      subtitle_race_bet_kind: '馬券種類',

      // データセット
      dataset_race_place: ['札幌', '函館', '福島'],
      dataset_race_num: [1,2,3,4,5,6,7,8,9,10,11,12],
      // dataset_race_bet_way: ['１点買い','軸１頭流し','軸２頭流し','ボックス','フォーメーション'],
      // dataset_race_bet_kind: ['単勝','複勝','馬単','馬連','枠連','ワイド','３連複','３連単'],
      dataset_race_bet_kind: ['単勝','複勝'],
      dataset_race_bet_way: ['１点買い'],


      // 入力データ
      input_race_place: '',
      input_race_num: '',
      input_race_bet_way: '',
      input_race_bet_kind: '',

      // 作成データ
      create_data: this.input_race_place,

      // create_data: "\n"+
      //   this.input_race_place+" "+
      //   this.input_race_num+"R\n"+
      //   this.input_race_bet_kind+"（"+
      //   this.input_race_bet_way+"）",
      
    }
  },
  methods: {
    selected_race_place: function (selected_data) {
      this.input_race_place = selected_data
    },
    selected_race_num: function (selected_data) {
      this.input_race_num = selected_data
    },
    selected_race_bet_way: function (selected_data) {
      this.input_race_bet_way = selected_data
    },
    selected_race_bet_kind: function (selected_data) {
      this.input_race_bet_kind = selected_data
    },
  }
}
</script>

