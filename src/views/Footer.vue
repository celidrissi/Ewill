s<template>
    <div class="row" id="footer">
        <div class="col-9 row" id="footer_left">
            <div class="col-6 col-md-6">© 2021 - El idrissi Chafik | </div>
            <div class="col-6" id="footer_img">
                <img alt="Be Hance" src="@/assets/images/icons/08_behance_t.png"/>
                <img alt="Dribbble" src="@/assets/images/icons/04_dribbble_t.png"/>
                <img alt="LinkedIn" src="@/assets/images/icons/07_linkedin_t.png"/>
                <img alt="Facebook" src="@/assets/images/icons/02_facebook_t.png"/>
                <img alt="Instagram" src="@/assets/images/icons/10_instagram_t.png"/>
                <img alt="Twitter" src="@/assets/images/icons/01_twitter_t.png"/>
            </div>
        </div>
        <div class="col row" id="footer_right">
            <div class="w-unset btn-round" id="footer_contact_btn" @click="$emit('open-modal', 'contact')">
                CONTACT
            </div>
        </div>
    </div>
</template>

<script>

export default {
  name: 'Footer',
};
</script>

<style scoped>
    #footer {
        background-color:#2B2A2C;
        position: relative;
        height: 100px;
    }
    #footer_right{
        max-width: fit-content;
    }
    #footer_left{}
    #footer_left > *, #footer_contact_btn {
        font-size: 20px;
        font-weight: normal;
        color: #8D8D8E;
        width: auto;
        margin-top: auto;
        margin-bottom: auto;
    }
    #footer_img{
        padding: 0;
    }
    #footer_img > img{
        margin-right: -20px;
    }
    #footer_contact_btn{
        height: fit-content;
        padding-left: 10px;
        padding-right: 10px;
        padding-top: 5px;
        padding-bottom: 5px;
        border-color: #8D8D8E;
    }
    #footer_contact_btn:hover {
        background: #8D8D8E;
        color: #2B2A2C;
    }
</style>
