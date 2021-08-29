<template>

<div>
    <!-- サブタイトル[Tag] -->
    <!-- <v-flex>
        競馬場：
        <transition name="fade" appear>
            <span v-if="button_click">
                <v-btn outlined rounded small>{{ selected_text }}</v-btn>
            </span>
        </transition>
    </v-flex> -->

    <!-- サブタイトル[Button] -->
    <v-container>  
      <!-- <div v-show="button_show"> -->

        <!-- <v-btn
            outlined
            rounded
            v-bind:style="styleObject"
            v-for="(value, key) in place_data" :key="key" 
            @click="clickSelected(value.place_name)"
        >{{ value.place_name }}</v-btn> -->

      <v-row align="center">
        
        <v-col class="d-flex" cols="4" sm="6">
          <div class="font-weight-black">競馬場</div>
        </v-col>

        <v-col class="d-flex pa-0" cols="8" sm="6">
          <!-- <v-select :items="place_name" label="選択してください"></v-select> -->
          <v-select
            :items="place_name" 
            :label="label_text" 
            @change="changeSelected()"
          ></v-select>
        </v-col>
      </v-row>
      <!-- </div>   -->
    </v-container>




</div>

</template>

<script>
export default {
  data() {
    return {
      label_text: "選択してください",
      styleObject:{color:'white'},
      text_show: false,
      button_click: false,
      button_show: true,
      selected_text: '',
      place_name: ['札幌', '函館', '福島'],
      place_data: [
        { place_code: '00', place_name: '札幌' },
        { place_code: '01', place_name: '函館' },
        { place_code: '02', place_name: '福島' },
      ],
    }
  },
  methods: {
    clickSelected: function (event) {
        this.button_click = true;
        this.button_show = false;
        this.selected_text = event;
        this.text_show = true;
        this.styleObject["color"] = 'grey';
    },
    changeSelected: function(event) {
        this.label_text = ""
    },
  }
}
</script>

<style scoped>
.fade-enter-active, .fade-leave-active {
  transition: opacity 0.8s;
}
.fade-enter, .fade-leave-to {
  opacity: 0;
}

</style>
