<template>

<div>
    
    <v-container>  

      <v-row align="center">

        <!-- サブタイトル[Tag] -->
        <v-col class="d-flex" cols="4" sm="6">
          <div class="font-weight-black">競馬場</div>
        </v-col>

        <!-- サブタイトル[Button] -->
        <v-col class="d-flex pa-0" cols="8" sm="6">
          <v-select
            :items="place_name" 
            :label="label_text" 
            @change="changeSelected()"
          ></v-select>
        </v-col>

      </v-row>
      
    </v-container>

</div>

</template>

<script>
export default {
  data() {
    return {
      label_text: "選択してください",
      place_name: ['札幌', '函館', '福島'],
    }
  },
  methods: {
    changeSelected: function(event) {
        this.label_text = ""
    },
  }
}
</script>
