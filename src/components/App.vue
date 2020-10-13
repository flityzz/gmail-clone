<template>
    <div id="grid">
        <EmailHeader />
        <EmailMenu />
        <EmailList />
        <AsideBar />
    </div>
</template>

<script>
import EmailHeader from './EmailHeader'
import EmailMenu from './EmailMenu'
import EmailList from './EmailList'
import AsideBar from './AsideBar'
export default {
  components: {
      EmailHeader,
      EmailMenu,
      EmailList,
      AsideBar
  }
}
</script>

<style scoped>

    #grid{
        display: grid;
        grid-template-columns: 252px auto 56px;
        grid-template-rows: 65px auto;
        grid-template-areas:
            "EH EH EH"
            "EM EL AB"; 
        height: 100vh;
    }
</style>
