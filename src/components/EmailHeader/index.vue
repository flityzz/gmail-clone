<template>
  <div class="email-header-container">
      <div class="header-menu">
          <div class="icon">
              <div></div>
              <div></div>
              <div></div>
          </div>
          <div class="img"><img src="../../assets/gmail-logo.png"  alt="logo"></div>
      </div>
      
      <div class="input-wrapper">
        <div class="search-icon"><SearchIcon :size="24"/></div>
        <input type="text" placeholder="Pesquisar e-mail">
        <div class="icon-menu-down"><MenuDown :size="24"/></div>
      </div>
      
      <div class="header-options">
          <div class="o-wrapper">
              <div class="icon-help"><HelpIcon :size="24"/></div>
              <div class="icon-settings"><SettingsIcon :size="24"/></div>
              <div class="icon-apps"><img class="svg-icon" src="../../assets/icons/dots-grid.svg" ></div>
              <div class="avatar">JS</div>
          </div>  
      </div>

  </div>
</template>

<script>

import SearchIcon from 'vue-material-design-icons/Magnify'
import MenuDown from 'vue-material-design-icons/MenuDown'
import HelpIcon from 'vue-material-design-icons/HelpCircleOutline'
import SettingsIcon from 'vue-material-design-icons/CogOutline'

export default {
    components: {
        SearchIcon,
        MenuDown,
        HelpIcon,
        SettingsIcon,
    }
}
</script>

<style scoped lang="scss">
    .email-header-container{
        grid-area: EH;
        display: flex;
        flex-direction: row;
        align-items: center;
        border: solid 1px var(--gmailgrey);
        padding: 31px 22px 31px 22px;
        
    .header-menu{
        display: flex;
        flex-direction: row;
        align-items: center;
        

        .icon {
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: center;
            cursor: pointer;
            height: 50px;
            width: 50px;
            > div {
                width: 19px;
                height: 2px;
                background-color: var(--grey);
                margin: 1.5px 0 1.5px 0
            }

            &:hover{
                background-color: var(--lgrey);
                border-radius: 50%;
                transition: 0.1s;
            }
        }

        .img {
            margin-left: 5px;
            cursor: pointer; 
        }
    }

    .input-wrapper {
        display: flex;
        flex-direction: row;
        align-items: center;
        margin-left: 64px;
        height: 48px;
        width: 720px;
        background-color: var(--gmailgrey);
        border-radius: 6px;
        padding: 0 10px 0 10px;

        @media (max-width: 1220px) {
                width: 100%;
        }
        
        .search-icon {
            color: var(--grey);
            height: 40px;
            width: 44px;
            display: flex;
            align-items: center;
            justify-content: center;
            padding-left: 2px;
            &:hover{
                background-color: var(--lgrey);
                border-radius: 50%;
            }
        }

        input {
            margin-left: 10px;
            width: 100%;

            text-align: left;
            opacity: 90%;
            background-color: var(--gmailgrey);
            font-size: 15px;
            position: relative;       
        }

        .icon-menu-down {
            color: var(--grey);
            height: 40px;
            width: 48px;
            padding:  0px 3px;
            display: flex;
            align-items: center;
            justify-content: center;
            
            &:hover{
                background-color: var(--lgrey);
                border-radius: 50%;
                transition: 0.1s;
            }
        }
    }

    .header-options {
        display: flex;
        flex-direction: row;
        align-items: center;
        justify-content: flex-end;
        margin-left: 48px;
        flex-grow: 1;
        
        .o-wrapper {
            display: flex;
            flex-direction: row;
            justify-content: space-between;
            width: 180px;
            align-items: center;

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

            .icon-help {
                color: var(--grey);
                height: 40px;
                width: 40px;
                padding:  0px 3px;
                display: flex;
                align-items: center;
                justify-content: center;
                cursor: pointer;
            
                    &:hover{
                    background-color: var(--lgrey);
                    border-radius: 50%;
                    transition: 0.1s;
                    }
            }

            .icon-settings{
                color: var(--grey);
                height: 40px;
                width: 40px;
                padding:  0px 3px;
                display: flex;
                align-items: center;
                justify-content: center;
                cursor: pointer;
            
                    &:hover{
                        background-color: var(--lgrey);
                        border-radius: 50%;
                        transition: 0.1s;
                    }
            }

            .icon-apps {
                height: 40px;
                width: 40px;
                padding:  0px 3px;
                display: flex;
                align-items: center;
                justify-content: center;
                cursor: pointer;
                
                    &:hover{
                        background-color: var(--lgrey);
                        border-radius: 50%;
                        transition: 0.1s;
                    }

                    .svg-icon {
                        filter: invert(38%) sepia(5%) saturate(516%) hue-rotate(173deg) brightness(94%) contrast(83%);
                        padding-bottom: 1px;
                    }
            }
        }
    }
}
</style>