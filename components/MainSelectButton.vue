<template>

    <v-container>

      <v-row align="center">
        
        <!-- サブタイトル[Tag] -->
        <v-col class="d-flex" cols="4" sm="6">
          <div class="font-weight-black">{{ props_title }}</div>
        </v-col>

        <!-- サブタイトル[Button] -->
        <v-col class="d-flex  pa-0" cols="8" sm="6">
            <v-select
              :items="props_data" 
              :label="label_text" 
              @change="changeSelected()"
            ></v-select>
        </v-col>
      
      </v-row>
      
    </v-container>

</template>


<script>
export default {
  props: ["subtitle", "dataset"],

  data() {
    return {
      props_title: this.subtitle,
      props_data: this.dataset,
      label_text: "選択してください",
    }
  },
  methods: {
    changeSelected: function(event) {
        this.label_text = ""
    },    
  }
}
</script>

