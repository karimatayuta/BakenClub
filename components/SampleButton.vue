<template>
  
  <v-container>  
    <div class="text-center">
      <v-btn outlined rounded>{{ button_text }}</v-btn>
    </div>
  </v-container>

</template>


<script>
export default {
  data() {
    return {
      button_text: "Create URL",
    }
  }
}
</script>
