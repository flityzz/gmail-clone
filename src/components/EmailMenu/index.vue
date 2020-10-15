<template>
  <div class="email-menu-container">
    <div class="menu-options">
      <div class="button-wrapper">
        <div class="plus-icon">
          <img
            src="https://www.gstatic.com/images/icons/material/colored_icons/1x/create_32dp.png"
            alt=""
          />
        </div>
        <span>Escrever</span>
      </div>

      <div class="itens">
        <Item
          name="Caixa de entrada"
          quantidade="19.607"
          isInbox
          hasNotification
          icon_url="https://www.gstatic.com/images/icons/material/system/1x/inbox_black_20dp.png"
        />
        <Item
          name="Com estrela"
          icon_url="https://www.gstatic.com/images/icons/material/system/1x/grade_black_20dp.png"
        />
        <Item
          name="Adiados"
          icon_url="https://www.gstatic.com/images/icons/material/system/1x/watch_later_black_20dp.png"
        />
        <Item
          name="Importante"
          icon_url="https://www.gstatic.com/images/icons/material/system/1x/label_important_black_20dp.png"
        />
        <Item
          name="Enviados"
          icon_url="https://www.gstatic.com/images/icons/material/system/1x/send_black_20dp.png"
        />
        <Item
          name="Rascunhos"
          hasNotification
          icon_url="https://www.gstatic.com/images/icons/material/system/1x/insert_drive_file_black_20dp.png"
        />
        <Item
          name="Mais"
          icon_url="https://www.gstatic.com/images/icons/material/system/1x/expand_more_black_20dp.png"
        />
      </div>
    </div>

    <div class="resize-button"></div>

    <div class="meets-container">
      <div class="meets-itens">
        <div class="title">Meet</div>
        <Item
          name="Iniciar uma reunião"
          icon_url="https://www.gstatic.com/images/icons/material/system/1x/videocam_black_20dp.png"
        />
        <Item
          name="Participar de reunião"
          icon_url="https://www.gstatic.com/images/icons/material/system/1x/keyboard_black_20dp.png"
        />
      </div>

      <div class="hangouts-container">
        <div class="title">Hangouts</div>
        <div class="user-wrapper">
          <div class="avatar-section">
            <div class="avatar">JS</div>
            <span>João</span>
            <div class="icon-menu-down"><MenuDown :size="20" /></div>
          </div>
          <div class="icon-plus"><Plus :size="20" /></div>
        </div>
      </div>

      <div class="hangouts-chat">
        <img src="../../assets/hangouts.png" alt="hangouts" />
        <p>Nenhum bate-papo recente</p>
        <a href="/">Iniciar um novo</a>
      </div>
    </div>
  </div>
</template>

<script>
import Item from "./Item";
import MenuDown from "vue-material-design-icons/MenuDown";
import Plus from "vue-material-design-icons/Plus";
export default {
  components: {
    Item,
    MenuDown,
    Plus,
  },
};
</script>

<style scoped lang="scss">
.email-menu-container {
  margin-top: 65px;
  grid-area: EM;
  display: flex;
  flex-direction: column;
  box-sizing: border-box;
  position: fixed;

  &:hover .resize-button {
    transition: 0.1s;
    background-color: var(--gmailgrey);
  }

  .menu-options {
    border-bottom: solid 1px var(--lgrey);
    resize: vertical;
    overflow-y: auto;
    overflow-x: hidden;

    min-height: 180px !important;
    max-height: 431px !important;

    &::-webkit-scrollbar {
      height: 9px;
      width: 9px;
    }

    &::-webkit-scrollbar-thumb {
      background-color: rgba(0, 0, 0, 0.2);
      -webkit-box-shadow: inset 1px 1px 0 rgba(0, 0, 0, 0.1),
        inset 0 -1px 0 rgba(0, 0, 0, 0.07);
    }

    &::-webkit-scrollbar-corner {
      background-color: transparent;
    }

    .button-wrapper {
      display: flex;
      flex-direction: row;
      height: 48px;
      width: 144px;
      border-style: border-box;
      box-shadow: 0 1px 2px 0 rgba(60, 64, 67, 0.302),
        0 1px 3px 1px rgba(60, 64, 67, 0.149);
      padding: 0 24px 0 0;
      overflow: hidden;
      border-radius: 24px;
      align-items: center;
      justify-content: center;
      background-color: #fff;
      cursor: pointer;
      font-size: 0.875rem;
      letter-spacing: 0.25px;
      margin: 16px 0 16px 8px;

      .plus-icon {
        margin-right: 10px;
      }

      &:hover {
        box-shadow: 0 1px 3px 0 rgba(60, 64, 67, 0.302),
          0 4px 8px 3px rgba(60, 64, 67, 0.149);
        transition: 0.1s;
        background-color: #fafafb;
      }
    }
  }

  .resize-button {
    border-radius: 2px;
    height: 6px;
    margin: 4px auto 0;
    width: 34px;
    cursor: row-resize;
  }

  .title {
    margin: 12px 12px 12px 26px;
    font-size: 0.875rem;
    letter-spacing: 0.25px;
    -webkit-border-radius: 0;
    border-radius: 0;
    color: var(--meetsBold);
    font-weight: 500;
  }

  .meets-container {
    height: 417px;
    display: flex;
    flex-direction: column;

    .meets-itens {
      display: flex;
      flex-direction: column;
      border-bottom: solid 1px var(--lgrey);
    }
  }

  .hangouts-container {
    display: flex;
    flex-direction: column;
    border-bottom: solid 1px var(--lgrey);
    margin-top: 12px;
    .user-wrapper {
      display: flex;
      flex-direction: row;
      justify-content: space-between;

      height: 32px;
      width: 240px;
      position: relative;
      padding: 0 12px 0 26px;
      box-sizing: border-box;
      border-radius: 0 16px 16px 0;
      align-items: center;

      .avatar-section {
        display: flex;
        flex-direction: row;
        align-items: center;
        cursor: pointer;
        .avatar {
          display: flex;
          width: 28px;
          height: 28px;
          border-radius: 50%;
          background-color: rgb(145, 65, 65);
          color: white;
          cursor: pointer;
          align-items: center;
          justify-content: center;
          padding-right: 1px;
        }

        span {
          margin: 0 -5px 0 5px;
          font-size: 0.8rem;
        }

        .icon-menu-down {
          height: 19px;
          filter: invert(55%) sepia(0%) saturate(378%) hue-rotate(219deg)
            brightness(83%) contrast(93%);
        }
      }

      .icon-plus {
        height: 29px;
        width: 29px;
        padding-top: 3px;
        display: flex;
        cursor: pointer;
        align-items: center;
        justify-content: center;
        filter: invert(55%) sepia(0%) saturate(378%) hue-rotate(219deg)
          brightness(83%) contrast(93%);

        &:hover {
          background-color: var(--lgrey-secondary);
          transition: 0.1s;
          border-radius: 50%;
        }
      }
    }
  }

  .hangouts-chat {
    margin-top: 12px;
    padding: 0 12px 0 26px;

    display: flex;
    flex-direction: column;
    align-items: center;
    img {
      margin: 12px 0 12px 0;
      width: 80px;
      height: 89px;
    }

    p,
    a {
      font-size: 0.875rem;
    }

    a {
      color: #1155cc;
    }
  }
}
</style>
