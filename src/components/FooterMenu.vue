<template>
  <div class="footer">
    <div class="footer-elements">
      <div class="footer-element">
        <span class="indicator-text">Cellnet</span>
        <img src="../img/indicator.png" alt="" />
      </div>
      <div class="footer-element">
        <span class="indicator-text">Mainnet</span>
        <img src="../img/indicator.png" alt="" />
      </div>
      <div class="footer-element">
        <span class="indicator-text">Somenet</span>
        <img src="../img/indicator.png" alt="" />
      </div>
      <div class="footer-element">
        <span class="indicator-text">Testnet</span>
        <img src="../img/indicator.png" alt="" />
      </div>
    </div>
  </div>
</template>
<style lang="scss">
.footer {
  display: flex;
  width: 100%;
  height: 42px;
  padding: 0px 50px;
  position: relative;
  /* justify-content: center;
  align-items: flex-start;
  flex-shrink: 0; */
  background: var(--main-b-gcolor, #2e3138);
  box-shadow: 5px -5px 10px 0px rgba(8, 7, 13, 0.42),
    1px 1px 0px 0px #524d64 inset;
}

.footer-elements {
  display: inline-flex;
}

.footer-element {
  width: 295px;
  height: 42px;
  flex-shrink: 0;
  display: flex;
  flex-direction: row;
  align-content: center;
  justify-content: center;
  align-items: center;
}

.indicator-text {
  color: #fff;
  text-align: right;
  font-feature-settings: "clig" off, "liga" off;
  font-family: Quicksand;
  font-size: 12px;
  font-style: normal;
  font-weight: 500;
  line-height: normal;
  margin-right: 8px;
}
</style>
