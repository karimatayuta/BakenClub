<template>
<div>

    <!-- サブタイトル[Tag] -->
    <!-- <v-flex>
        {{ props_title }}：
        <transition name="fade" appear>
            <span v-if="button_click">
                <v-btn outlined rounded small>{{ selected_text }}</v-btn>
            </span>
        </transition>
    </v-flex> -->

    <!-- サブタイトル[Button] -->
    <!--
        v-for="number in race_numbers" 
        :key="number.id"
    -->

    <v-container>
      <!-- <div v-show="button_show"> -->

        <!-- <v-btn
            outlined
            rounded
            small
            v-bind:style="styleObject"
            v-for="data in props_data" :key="data.id"
            @click="clickSelected(data)"
        >{{ data }}</v-btn> -->
        
        
      <v-row align="center">
        
        <v-col class="d-flex" cols="4" sm="6">
          <div class="font-weight-black">{{ props_title }}</div>
        </v-col>

        <v-col class="d-flex  pa-0" cols="8" sm="6">
            <v-select
              :items="props_data" 
              :label="label_text" 
              @change="changeSelected()"
            ></v-select>
        </v-col>
      </v-row>
      <!-- </div> -->
    </v-container>


</div>
</template>



<script>
export default {
  props: ["subtitle", "dataset"],

  data() {
    return {
      props_title: this.subtitle,
      props_data: this.dataset,
      styleObject:{color:'white'},
      text_show: false,
      button_click: false,
      button_show: true,
      selected_text: '',
      label_text: "選択してください",
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