<template>
  <div class="aside-container">
    <div>
      <img
        src="https://www.gstatic.com/companion/icon_assets/calendar_2x.png"
        alt=""
      />
    </div>
    <div>
      <img
        src="https://www.gstatic.com/companion/icon_assets/tasks2_2x.png"
        alt=""
      />
    </div>
    <div>
      <img
        src="https://www.gstatic.com/companion/icon_assets/keep_2x.png"
        alt=""
      />
    </div>
  </div>
</template>

<script>
export default {};
</script>

<style scoped lang="scss">
.aside-container {
  grid-area: AB;
  display: flex;
  flex-direction: column;
  align-items: center;
  background-color: #fff;
  z-index: 20;
  border-left: solid 1px var(--lgrey);

  > div {
    padding-top: 30px;
    > img {
      height: 20px;
      width: 20px;
    }
  }
}
</style>
