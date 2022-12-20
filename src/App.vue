<template>
  <div>
      <j-avatar initials-name="Inna Pav"></j-avatar>
      <j-button text="hfhfhfhf"></j-button>
  </div>
  <router-view/>
</template>

<script setup lang="ts">
import {computed, defineProps} from "vue";
import JAvatar from "@/components/UI/J-avatar/J-avatar.vue";
import JButton from "@/components/UI/J-button/J-button.vue";

</script>

<style lang="scss">
@import "https://cdn.jsdelivr.net/npm/bootstrap@5.2.3/dist/css/bootstrap.min.css";
</style>
