<template>
  <div class="bg-menu">
    <div class="bg-logo">
      <img src="../img/logo.png" alt="" />
    </div>
    <div class="menu-icon">
      <img class="icon" src="../img/wallet.png" alt="" />
      <span class="icon-text">Wallet</span>
    </div>
    <div class="menu-icon">
      <img class="icon" src="../img/dex.png" alt="" />
      <span class="icon-text">DEX</span>
    </div>
    <div class="menu-icon">
      <img class="icon" src="../img/tx_explorer.png" alt="" />
      <span class="icon-text">TX explorer</span>
    </div>
    <div class="menu-icon--active">
      <img class="icon" src="../img/certificate.png" alt="" />
      <span class="icon-text">Certificates</span>
    </div>
    <div class="menu-icon">
      <img class="icon" src="../img/tokens.png" alt="" />
      <span class="icon-text">Tokens</span>
    </div>
    <div class="menu-icon">
      <img class="icon" src="../img/vpn.png" alt="" />
      <span class="icon-text">VPN client</span>
    </div>
    <div class="menu-icon">
      <img class="icon" src="../img/vpn_service.png" alt="" />
      <span class="icon-text">VPN service</span>
    </div>
    <div class="menu-icon">
      <img class="icon" src="../img/console.png" alt="" />
      <span class="icon-text">Console</span>
    </div>
    <div class="menu-icon">
      <img class="icon" src="../img/logs.png" alt="" />
      <span class="icon-text">Logs</span>
    </div>
    <div class="menu-icon">
      <img class="icon" src="../img/settings.png" alt="" />
      <span class="icon-text">Settings</span>
    </div>
    <div class="menu-icon">
      <img class="icon" src="../img/dapps.png" alt="" />
      <span class="icon-text">dApps</span>
    </div>
    <!-- Здесь можно разместить иконки и текст -->
  </div>
</template>

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
  &--active {
    border-radius: 0px 16px 16px 0px;
    background: var(--main-b-gcolor, #2e3138);

    display: inline-flex;
    padding: 14px 38px 14px 24px;
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

  /* body13pxRegular */
  font-family: Quicksand;
  font-size: 13px;
  font-style: normal;
  font-weight: 400;
  line-height: normal;
  text-wrap: nowrap;
  /* margin-left: 16px; */
}

.icon {
  display: flex;
  /* width: 16px;
  height: 16px; */
  /* height: 24px; */
  justify-content: center;
  align-items: center;
  gap: 10px;
  margin-left: 24px;
}
</style>
