<template>
  <div class="email-wrapper" :class="{ isReaded: isReaded }">
    <div class="icons">
      <div class="icon-box"><CheckBox :size="21" /></div>
      <div class="icon-star"><StarIcon :size="21" /></div>
      <div class="icon-mark"><IconMark :size="21" /></div>
    </div>

    <div class="title"><strong>Titulo do Email</strong></div>

    <div class="body">
      <div class="header">
        <strong :class="{ isReaded: isReaded }"
          >Isso é um cabeçalho do email</strong
        >
        <div class="separator">-</div>
        <p>
          Isso é a mensagem do email
          BlaBlaBlaBlaBlaBlaBlaBlaBlaBlaBlaBlaBlaBlaBlaBlaBlaBlaBlaBlaBlaBlaBlaBlaBlaBlaBlaBlaBlaBlavadasdadasdasdadsadasdadadadadadadadasdadasda
        </p>
      </div>

      <div class="time">20:06</div>
    </div>
  </div>
</template>

<script>
import CheckBox from "vue-material-design-icons/CheckboxBlankOutline";
import StarIcon from "vue-material-design-icons/StarOutline";
import IconMark from "vue-material-design-icons/LabelOutline";
export default {
  props: {
    isReaded: Boolean,
  },
  components: {
    CheckBox,
    StarIcon,
    IconMark,
  },
};
</script>

<style scoped lang="scss">
.email-wrapper {
  z-index: 5;
  height: 40px;
  display: flex;
  flex-direction: row;
  align-items: center;
  padding-right: 18px;
  font-size: 0.875rem;
  cursor: pointer;
  border-bottom: solid 1px var(--gmailgrey);

  &:hover {
    -webkit-box-shadow: inset 0 -1px 0 0 rgba(100, 121, 143, 0.122);
    box-shadow: inset 0 -1px 0 0 rgba(100, 121, 143, 0.274);
    border-left: solid 1px var(--gmailgrey);
    border-right: solid 1px var(--gmailgrey);
  }

  .icons {
    display: flex;
    flex-direction: row;

    > div {
      padding: 0px 0 0 12px;
    }

    .icon-box,
    .icon-star,
    .icon-mark {
      filter: invert(86%) sepia(1%) saturate(89%) hue-rotate(314deg)
        brightness(90%) contrast(98%);

        &:hover{
          filter: invert(0%) sepia(95%) saturate(47%) hue-rotate(254deg)
          brightness(100%) contrast(100%);
        }
    }
  }

  .title {
    display: flex;
    margin-left: 20px;
    flex-direction: row;
    justify-content: flex-start;
    width: 200px;
    padding-right: 32px;
  }

  .body {
    flex-grow: 1;
    display: flex;
    flex-direction: row;
    justify-content: space-between;

    .header {
      display: flex;
      flex-direction: row;

      p {
        width: 600px;
        white-space: nowrap;
        overflow: hidden;
        text-overflow: ellipsis;
      }
    }

    .separator {
      margin: 0 10px 0 10px;
    }
  }
}

.isReaded {
  background-color: var(--gmailbody);
  strong {
    font-weight: normal;
  }
}
</style>
