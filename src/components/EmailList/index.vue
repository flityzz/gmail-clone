<template>
  <div class="email-list-container">
    <div class="email-list-actions">
      <div class="icon-box"><CheckBox :size="21" /></div>
      <div class="icon-menu-down"><MenuDown :size="20" /></div>

      <div class="icon-refresh"><Refresh :size="21" /></div>
      <div class="icon-more"><More :size="21" /></div>
    </div>

    <div class="email-list">
      <div class="nao-lidas">

      </div>

      <div class="todas-as-demais">

      </div>
      
    </div>
  </div>
</template>

<script>
import MenuDown from "vue-material-design-icons/MenuDown";
import CheckBox from "vue-material-design-icons/CheckboxBlankOutline";
import Refresh from "vue-material-design-icons/Refresh";
import More from "vue-material-design-icons/DotsVertical";

export default {
  components: {
    MenuDown,
    CheckBox,
    Refresh,
    More,
  },
};
</script>

<style scoped lang="scss">
.email-list-container {
  grid-area: EL;

  display: flex;
  flex-direction: column;

  .email-list-actions {
    height: 48px;

    display: flex;
    flex-direction: row;
    justify-content: flex-start;
    align-items: center;
    border-bottom: solid 1px var(--gmailgrey);

    .icon-box,
    .icon-menu-down,
    .icon-refresh,
    .icon-more {
      cursor: pointer;
      filter: invert(55%) sepia(0%) saturate(378%) hue-rotate(219deg)
      brightness(83%) contrast(93%);

      &:hover{
        transition: 0.1s;
        border-radius: 2px;
        filter: invert(0%) sepia(95%) saturate(47%) hue-rotate(254deg) brightness(100%) contrast(100%);
      }
    }

    .icon-box {
      margin: 0 -5px 0 12px;
    }

    .icon-refresh{
      margin: 0 15px 0 15px;
    }
  }
}
</style>
