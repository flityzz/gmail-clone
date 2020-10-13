<template>
  <div class="item-container" :style="inboxContainer">
    <div class="icon">
      <img class="svg-icon" :src="iconResolver" alt="" />
    </div>

    <div class="text-field">
      <span :class="{ 'has-notification': hasNotification }">{{ name }}</span>
      <span :class="{ qtd: quantidade }">{{ quantidade }}</span>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    name: String,
    icon_url: String,
    isInbox: Boolean,
    quantidade: String,
    hasNotification: Boolean,
  },

  computed: {
    inboxContainer() {
      return this.isInbox
        ? {
            background: "rgba(216, 55, 55, 0.123)",
            color: "#d93025",
          }
        : {};
    },

    iconResolver() {
      return this.isInbox
        ? "https://www.gstatic.com/images/icons/material/system/1x/inbox_gm_googlered600_20dp.png"
        : this.icon_url;
    },
  },
};
</script>

<style scoped lang="scss">
.item-container {
  display: flex;
  flex-direction: row;
  font-size: 0.875rem;
  margin-left: 0px;
  height: 32px;
  width: 240px;
  position: relative;
  padding: 0 12px 0 26px;
  cursor: pointer;
  box-sizing: border-box;
  border-radius: 0 16px 16px 0;
  align-items: center;

  &:hover {
    background-color: var(--gmailgrey);
  }

  .icon {
    display: flex;
    flex-shrink: 0;
    justify-content: flex-start;
    margin-right: 18px;
    height: 20px;
    width: 20px;

    .svg-icon {
      filter: invert(38%) sepia(5%) saturate(516%) hue-rotate(173deg)
        brightness(94%) contrast(83%);
      padding-bottom: 1px;
    }
  }

  .text-field span {
    overflow: hidden;
    text-overflow: ellipsis;
    white-space: nowrap;
    margin-right: 10px;
  }

  .has-notification,
  .qtd {
    font-weight: bold;
  }
}
</style>
