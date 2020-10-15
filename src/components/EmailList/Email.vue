<template>
  <div class="email-wrapper" :class="{ isReaded: isReaded }">
    <div class="icons">
      <div class="icon-box">box</div>
      <div class="icon-star">star</div>
      <div class="icon-mark">mark</div>
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
export default {
  props: {
    isReaded: Boolean,
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
  }

  .icons {
    display: flex;
    flex-direction: row;

    > div {
      padding: 0px 10px 0 12px;
    }
  }

  .title {
    display: flex;
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
