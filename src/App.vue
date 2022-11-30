<template>
  <div>
      <j-button :text="'Hello'"></j-button>
  </div>
  <router-view/>
</template>

<script>
import JButton from "@/components/UI/J-button/J-button";
export default {
    components: {JButton}
}
</script>

<style lang="scss">

</style>
