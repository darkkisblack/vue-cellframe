<template>
  <div class="general-section">
    <BgMenu />
    <CentralSection />
    <FooterMenu />
  </div>
</template>
<script>
import BgMenu from "@/components/BgMenu.vue";
import CentralSection from "@/components/CentralSection.vue";
import FooterMenu from "@/components/FooterMenu.vue";
export default {
  name: "HomePage",
  components: {
    BgMenu,
    CentralSection,
    FooterMenu,
  },
};
</script>
<style lang="scss">
.general-section {
  display: flex;
  flex-wrap: wrap;
}
</style>
