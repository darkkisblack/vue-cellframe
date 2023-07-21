<template>
  <div class="central-section">
    <div class="search-bar">
      <div class="search-container">
        <i class="search-icon"><img src="../img/search.png" alt="" /></i>
        <input type="text" placeholder="Search" class="search-input" />
      </div>
    </div>
    <div class="central-container">
      <div class="filtered-table">
        <h2 class="table-title">{{ activeMenuItem }}</h2>
        <table>
          <thead>
            <tr>
              <th class="table-subtitle">
                <span class="filtered-text">{{ activeFilter }}</span>
              </th>
            </tr>
          </thead>
          <tbody>
            <tr
              class="td-content"
              v-for="certificate in certificates"
              :key="certificate"
            >
              <td class="td-text">{{ certificate }}</td>
            </tr>
          </tbody>
        </table>
      </div>
    </div>
    <div class="right-container">
      <h2 class="table-title filter-title">Filter</h2>
      <div class="radio-buttons">
        <div
          class="radio-button"
          @click="handleRadioClick(1, 'Public certificates')"
        >
          <img
            class="radio-image"
            :src="
              radioState === 1
                ? require('@/img/radio_active.png')
                : require('@/img/radio.png')
            "
            alt=""
            id="radio1"
          />
          <label class="radio-label" for="radio1">Public certificates</label>
        </div>
        <div
          class="radio-button"
          @click="handleRadioClick(2, 'Private certificates')"
        >
          <img
            class="radio-image"
            :src="
              radioState === 2
                ? require('@/img/radio_active.png')
                : require('@/img/radio.png')
            "
            alt=""
            id="radio2"
          />
          <label class="radio-label" for="radio2">Private certificates</label>
        </div>
        <div class="radio-button" @click="handleRadioClick(3, 'Both')">
          <img
            class="radio-image"
            :src="
              radioState === 3
                ? require('@/img/radio_active.png')
                : require('@/img/radio.png')
            "
            alt=""
            id="radio3"
          />
          <label class="radio-label" for="radio3">Both</label>
        </div>
      </div>
      <h2 class="table-title action-title">Actions</h2>
      <div class="action-buttons">
        <div class="action-button--btn_active">
          <span class="button-text">Create certificate</span>
        </div>
        <div class="action-button--btn_active">
          <span class="button-text">Import certificate</span>
        </div>
        <div class="action-button">
          <span class="button-text">Export private certificate to public</span>
        </div>
        <div class="action-button">
          <span class="button-text">Export certificate to mempool</span>
        </div>
        <div class="action-button">
          <span class="button-text">Delete certificate</span>
        </div>
      </div>
    </div>
  </div>
</template>
<script>
import arr from "./data";
import { eventBus } from "../main";
export default {
  name: "CentralSection",
  data() {
    return {
      certificates: arr,
      activeMenuItem: "Certificates",
      activeFilter: "Public certificates",
      radioState: 1,
    };
  },

  methods: {
    handleRadioClick(option, filterName) {
      this.radioState = option;
      this, (this.activeFilter = filterName);
      eventBus.$emit("radioOptionChanged", option);
    },
  },

  mounted() {
    eventBus.$on("menuItemClicked", (menuItemText) => {
      this.activeMenuItem = menuItemText;
    });
  },
};
</script>

<style lang="scss">
.central-section {
  display: flex;
  max-width: 100%;
  margin-left: 3px;
  flex-wrap: wrap;
}
.search-bar {
  display: flex;
  width: 100%;
  height: 60px;
  flex-shrink: 0;
  border-radius: 0px 0px 0px 16px;
  background: var(--main-b-gcolor, #2e3138);
  box-shadow: 1px 1px 0px 0px #524d64 inset,
    5px 5px 10px 0px rgba(8, 7, 13, 0.42);
}

.search-container {
  display: flex;
  width: 224px;
  height: 30px;
  flex-shrink: 0;
  border-bottom: 1px solid;
  border-color: #393b41;
  background: var(--main-b-gcolor, #2e3138);
  align-items: center;
  margin-top: 17px;
  margin-left: 36px;
}

.search-input {
  background: var(--main-b-gcolor, #2e3138);
  stroke-width: 1px;
  stroke: #393b41;
  border: none;
}

.search-input:focus {
  outline: none;
}

.search-icon {
  margin-right: 16px;
}

.central-container {
  display: flex;
  width: 678px;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  margin-left: 24px;
}

.filtered-table {
  display: flex;
  width: 678px;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  border-radius: 12px;
  background: var(--right-panel-color, #363a42);
  box-shadow: 3px 3px 5px 0px rgba(8, 7, 13, 0.25) inset,
    1px 1px 0px 0px rgba(107, 102, 126, 0.49);
  margin: 24px 24px 22px 24px;
}

.table-title {
  color: #fff;
  font-feature-settings: "clig" off, "liga" off;
  font-family: Quicksand;
  font-size: 14px;
  font-style: normal;
  font-weight: 700;
  line-height: normal;
  display: flex;
  height: 42px;
  padding: 0px 583px 0px 16px;
  align-items: center;
  margin: 0;
}

.table-subtitle {
  color: var(--text-color-white, #fff);
  font-feature-settings: "clig" off, "liga" off;
  font-family: Quicksand;
  font-size: 12px;
  font-style: normal;
  font-weight: 500;
  line-height: normal;
  width: 678px;
  height: 30px;
  flex-shrink: 0;
  fill: #2e3138;
  background: #2e3138;
  align-items: center;
  display: flex;
}

.td-text {
  color: var(--text-color-white, #fff);
  font-feature-settings: "clig" off, "liga" off;
  font-family: Quicksand;
  font-size: 16px;
  font-style: normal;
  font-weight: 400;
  line-height: 24px;
}

.td-content {
  display: flex;
  height: 50px;
  padding: 0px 589px 0px 0px;
  align-items: center;
  margin-left: 16px;
  margin-right: 16px;
  border-bottom: 1px solid var(--main-b-gcolor, #2e3138);
  background: var(--right-panel-color, #363a42);
}

.filtered-text {
  margin-left: 21px;
}

.right-container {
  width: 323px;
  margin-left: 40px;
}

label {
  display: inline-block;
  color: #fff;
  font-feature-settings: "clig" off, "liga" off;
  font-family: Quicksand;
  font-size: 16px;
  font-style: normal;
  font-weight: 400;
  line-height: 20px; /* 125% */
  cursor: pointer;
}

.radio-buttons {
  display: flex;
  flex-direction: column;
  align-items: flex-start;
}

.radio-button {
  margin-bottom: 32px;
  display: flex;
  align-items: center;
}

.radio-button:last-child {
  margin-bottom: 40px;
}

.filter-title {
  padding-left: 0px;
  margin-top: 30px;
}

.filter-title:last-child {
  margin-top: 0px;
  padding-top: 0px;
}

.action-title {
  padding-top: 0px;
  padding-left: 0px;
  margin-bottom: 24px;
}

.radio-label {
  margin-left: 16px;
}

.radio-image {
  cursor: pointer;
}

.action-button {
  display: flex;
  width: 318px;
  height: 36px;
  padding: 0px 40px;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  flex-shrink: 0;
  border-radius: 30px;
  border-radius: 30px;
  background: #b0aeb9;
  box-shadow: 1px 1px 4px 0px rgba(241, 231, 255, 0.3) inset,
    2px 2px 7px 0px rgba(11, 10, 13, 0.44);
  cursor: pointer;
  margin-bottom: 20px;

  &--btn_active {
    display: flex;
    width: 318px;
    height: 36px;
    padding: 0px 40px;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    flex-shrink: 0;
    border-radius: 30px;
    background: var(
      --main-button-color,
      linear-gradient(230deg, #9580ff 0%, #a361ff 100%)
    );
    box-shadow: 1px 1px 4px 0px #f1e7ff inset,
      2px 2px 7px 0px rgba(11, 10, 13, 0.44);
    cursor: pointer;
    margin-bottom: 20px;
  }
}

.action-button:hover {
  background: var(
    --main-hover-gradient,
    linear-gradient(90deg, #7930de 0%, #7f65ff 100%)
  );
}

.action-button:last-child {
  margin-bottom: 0px;
}
</style>
