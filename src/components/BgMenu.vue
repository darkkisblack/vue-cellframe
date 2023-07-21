<template>
  <div class="bg-menu">
    <div class="bg-logo">
      <img src="../img/logo.png" alt="" />
    </div>
    <div
      v-for="menuItem in menuItems"
      :key="menuItem.id"
      class="menu-icon"
      @click="toggleActive(menuItem)"
      :class="{ 'menu-icon--active': activeId === menuItem.id }"
    >
      <img class="icon" :src="menuItem.icon" alt="" />
      <span class="icon-text">{{ menuItem.text }}</span>
    </div>
  </div>
</template>

<script>
import { eventBus } from "../main";
export default {
  name: "BgMenu",
  data() {
    return {
      activeId: 4,
      menuItems: [
        { id: 1, icon: require("@/img/wallet.png"), text: "Wallet" },
        { id: 2, icon: require("@/img/dex.png"), text: "DEX" },
        { id: 3, icon: require("@/img/tx_explorer.png"), text: "TX explorer" },
        { id: 4, icon: require("@/img/certificate.png"), text: "Certificates" },
        { id: 5, icon: require("@/img/tokens.png"), text: "Tokens" },
        { id: 6, icon: require("@/img/vpn.png"), text: "VPN client" },
        { id: 7, icon: require("@/img/vpn_service.png"), text: "VPN service" },
        { id: 8, icon: require("@/img/console.png"), text: "Console" },
        { id: 9, icon: require("@/img/logs.png"), text: "Logs" },
        { id: 10, icon: require("@/img/settings.png"), text: "Settings" },
        { id: 11, icon: require("@/img/dapps.png"), text: "dApps" },
      ],
    };
  },

  methods: {
    toggleActive(menuItem) {
      this.activeId = this.activeId === menuItem.id ? null : menuItem.id;
      eventBus.$emit("menuItemClicked", menuItem.text);
    },
  },
};
</script>

<style lang="scss">
.bg-menu {
  width: 180px;
  height: 673px;
  flex-shrink: 0;
  fill: #2d3037;
  box-shadow: 5px 5px 10px 0px rgba(8, 7, 13, 0.42),
    1px 1px 0px 0px #524d64 inset;
  border-radius: 0px 0px 16px 0px;
}

.bg-logo {
  margin-left: 24px;
  margin-right: 47px;
  margin-top: 20px;
  margin-bottom: 20px;
}

.menu-icon {
  display: inline-flex;
  padding: 14px 68px 14px 24px;
  align-items: center;
  gap: 16px;
  cursor: pointer;
  &--active {
    border-radius: 0px 16px 16px 0px;
    background: var(--main-b-gcolor, #2e3138);

    display: inline-flex;
    padding: 0;
    width: 170px;
    height: 52px;
    align-items: center;
    gap: 16px;
    box-shadow: 3px 3px 5px 0px rgba(8, 7, 13, 0.25) inset,
      1px 1px 0px 0px rgba(107, 102, 126, 0.49);
    margin-right: 10px;
  }
  margin-right: 10px;
}

.icon-text {
  color: var(--text-color-white, #fff);
  font-feature-settings: "clig" off, "liga" off;
  font-family: Quicksand;
  font-size: 13px;
  font-style: normal;
  font-weight: 400;
  line-height: normal;
  text-wrap: nowrap;
}

.icon {
  display: flex;
  justify-content: center;
  align-items: center;
  gap: 10px;
  margin-left: 24px;
}
</style>
