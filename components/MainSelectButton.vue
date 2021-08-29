<template>

    <v-container class="pa-2">

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
            v-model="selected_data"
            @change="changeSelected(selected_data)"
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
      selected_data: "",
    }
  },
  methods: {
    changeSelected: function(event) {
      this.label_text = ""
      this.$emit('select_data', event)
      // alert(event)
    },   
  },
}
</script>

