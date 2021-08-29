<template>
  <div>
    <!-- baken_club -->

    <!-- <p class="text-justify"></p> -->
    <!-- 競馬場 -->
    <SampleButton></SampleButton>

    <!-- レース番号 -->
    <MainSelectButton 
      :subtitle="subtitle_race_num" 
      :dataset="dataset_race_num"
    ></MainSelectButton>

    <!-- 馬券種類 -->
    <MainSelectButton
      :subtitle="subtitle_race_bet_kind"
      :dataset="dataset_race_bet_kind"
    ></MainSelectButton>

    <!-- 購入方法 -->
    <MainSelectButton
      :subtitle="subtitle_race_bet_way"
      :dataset="dataset_race_bet_way"
    ></MainSelectButton>

    <MainTableData></MainTableData>

  </div>

</template>

<script>
// Sample.vueを読み込む
import SampleButton from '~/components/SampleButton.vue'
import MainSelectButton from '~/components/MainSelectButton.vue'
import MainTableData from '~/components/MainTableData.vue'

export default {
  components: {
    SampleButton,
    MainSelectButton,
    MainTableData,
  },
  data() {
    return {
      // サブタイトル
      subtitle_race_num: 'レース番号',
      subtitle_race_bet_way: '購入方法',
      subtitle_race_bet_kind: '馬券種類',

      // データセット
      dataset_race_num: [1,2,3,4,5,6,7,8,9,10,11,12],
      dataset_race_bet_way: ['１点買い','軸１頭流し','軸２頭流し','ボックス','フォーメーション'],
      dataset_race_bet_kind: ['単勝','複勝','馬単','馬連','枠連','ワイド','３連複','３連単'],
    }
  }
}
// console.log(this.selected)
</script>

