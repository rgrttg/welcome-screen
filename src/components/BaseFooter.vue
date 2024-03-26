<script setup>
</script>

<template>
  <div class="banner">
    <!-- the layout should support the dimensions: 1080 x 1920 -->
    <img alt="Logo der Stadt Zürich" class="" src="../assets/STZH_SEB_Logo.png" width="230" height="44"/>
    <img alt="Logo von Opportunity Zürich" src="../assets/Opportunity.png" height="48"/>
    <img alt="Logo SAG" src="../assets/SAG_Logo_De.png" height="52"/>
  </div>
</template>

<style scoped>
.banner {
  display: flex;
  flex-direction: row;
  flex-wrap: nowrap;
  justify-content: space-around;
  align-items: center;
  background-color: var(--color-background-footer);
  width: 1080px;
  height: 130px;
  /* top: 1790; */
}
</style>
