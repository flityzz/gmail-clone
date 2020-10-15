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
        <div class="title-wrapper">
          <div class="icon-arrow-up">
            <img
              src="https://www.gstatic.com/images/icons/material/system/1x/keyboard_arrow_up_black_20dp.png"
              alt="arrow"
            />
          </div>
          <div class="title">Não lidas</div>
        </div>

        <div class="info">
          <span>1–5 de 19.634</span>
          <div class="icon-dots">
            <img
              src="https://www.gstatic.com/images/icons/material/system/1x/more_vert_black_20dp.png"
              alt="dots"
            />
          </div>
        </div>
      </div>
      <div class="emails">
        <Email v-for="em in 5" :key="em.id"/>
      </div>

      <div class="todas-as-demais">
        <div class="title-wrapper">
          <div class="icon-arrow-up">
            <img
              src="https://www.gstatic.com/images/icons/material/system/1x/keyboard_arrow_up_black_20dp.png"
              alt="arrow"
            />
          </div>
          <div class="title">Todas as demais</div>
        </div>

        <div class="info">
          <span>1–25 de 79.634</span>
          <div class="icon-dots">
            <img
              src="https://www.gstatic.com/images/icons/material/system/1x/more_vert_black_20dp.png"
              alt="dots"
            />
          </div>
        </div>
      </div>

      <div class="emails">
        <Email v-for="em in 25" :key="em.id"/>
      </div>
    </div>
  </div>
</template>

<script>
import MenuDown from "vue-material-design-icons/MenuDown";
import CheckBox from "vue-material-design-icons/CheckboxBlankOutline";
import Refresh from "vue-material-design-icons/Refresh";
import More from "vue-material-design-icons/DotsVertical";

import Email from "./Email";

export default {
  components: {
    MenuDown,
    CheckBox,
    Refresh,
    More,
    Email,
  },
};
</script>

<style scoped lang="scss">
.email-list-container {
  grid-area: EL;

  display: flex;
  flex-direction: column;

  .email-list-actions {
    height: 60px;
    position: fixed;
    width: 100%;
    background-color: #fff;
    border-bottom: solid 1px var(--lgrey);
    border-top: solid 1px var(--lgrey);
    display: flex;
    flex-direction: row;
    justify-content: flex-start;
    align-items: center;
    
    .icon-box,
    .icon-menu-down,
    .icon-refresh,
    .icon-more {
      cursor: pointer;
      filter: invert(55%) sepia(0%) saturate(378%) hue-rotate(219deg)
        brightness(83%) contrast(93%);

      &:hover {
        transition: 0.1s;
        border-radius: 2px;
        filter: invert(0%) sepia(95%) saturate(47%) hue-rotate(254deg)
          brightness(100%) contrast(100%);
      }
    }

    .icon-box {
      margin: 0 -5px 0 12px;
    }

    .icon-refresh {
      margin: 0 15px 0 15px;
    }
  }

  .nao-lidas,
  .todas-as-demais {
    display: flex;
    flex-direction: row;
    justify-content: space-between;
    border-bottom: solid 1px var(--lgrey);
    padding: 5px 0 5px 0;
  }

  .nao-lidas {
    padding-top: 55px;
  }

  .title-wrapper {
    display: flex;
    flex-direction: row;
    align-items: center;
    justify-content: center;
    margin-top: 10px;
    box-sizing: border-box;
    padding: 0 10px 0 8px;

    
    cursor: pointer;

    font-size: 1rem;
    letter-spacing: 0.1px;
    font-variant-ligatures: no-contextual;
    color: #202124;
    font-weight: 500;
    line-height: 24px;

    height: 40px;

    .icon-arrow-up {
      height: 50%;
      margin-right: 10px;
    }

    &:hover {
      transition: 0.2s;
      background-color: var(--lgrey-secondary);
      border-radius: 6px;
    }
  }

  .info {
    display: flex;
    flex-direction: row;

    align-items: center;
    justify-content: center;
    margin-top: 10px;
    box-sizing: border-box;
    padding: 0 10px 0 8px;

    span {
      font-size: 0.75rem;
      letter-spacing: 0.3px;
      color: #5f6368;
      padding: 3px 10px 0 10px;

      display: flex;
      flex-direction: row;
      justify-content: center;
      align-items: center;
      cursor: pointer;
      height: 40px;
      &:hover {
        transition: 0.2s;
        background-color: var(--lgrey-secondary);
        border-radius: 6px;
      }
    }

    .icon-dots {
      cursor: pointer;
      height: 40px;
      width: 40px;
      display: flex;
      flex-direction: row;
      justify-content: center;
      align-items: center;

      &:hover {
        transition: 0.2s;
        background-color: var(--lgrey-secondary);
        border-radius: 6px;
        border-radius: 50%;
      }
    }
  }
}
</style>
