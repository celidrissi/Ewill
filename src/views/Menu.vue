<template>
    <div class="row itm-center">
        <div class="col col-xs-12 col-sm-12 col-md-6" id="profile">
            <div class="row py-5">
                <div class="w-unset" id="profile_photo">
                    <img
                    class="rounded-circle rounded-photo"
                    alt="Profile Photo"
                    src="@/assets/images/lewis.png"/>
                </div>
                <div class="w-unset p-0" id="profile_info">
                    <div class="col-12" id="profile_name">Lewis</div>
                    <div class="col-12" id="profile_surname">Nathaniel</div>
                    <div class="col-12" id="profile_job">UI & UX designer</div>
                </div>
            </div>
        </div>
        <div class="col col-xs-12 col-sm-12 col-md-6" id="menu">
            <div class="row w-unset" id="menu-item">
                <div class="col w-unset selected" id="menu_products">
                    PROJETS
                </div>
                <div class="col w-unset" id="menu_about">
                    A PROPOS
                </div>
                <div class="col w-unset" id="menu_blog">
                    BLOG
                </div>
                <div class="col w-unset btn-round" id="menu_contact">
                    CONTACT
                </div>
            </div>
        </div>
    </div>
</template>

<script>
export default {
  name: 'Menu',
};
</script>

<style scoped>
    * {
        font-size: 14px;
        font-weight: bold;
    }
    .rounded-photo{
        border-radius: 50%;
    }
    .w-unset{
        width: unset;
    }
    .itm-center{
        align-items: center;
    }
    .selected{
        text-decoration: underline;
        text-decoration-thickness: 3px;
        text-underline-position: under;
    }
    #menu_contact{
        max-width: fit-content;
    }
    #menu_contact:hover {
        background: #2B2A2C;
        color: #8D8D8E;
    }
    #profile_name{
        font-size: 16px;
        font-weight: bold;
    }
    #profile_surname{
        font-size: 16px;
        font-weight: bold;
    }
    #profile_job{
        font-size: 12px;
        font-weight: normal;
    }
</style>
