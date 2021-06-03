<template>
    <div class="row" id="footer">
        <div class="col" id="footer_left">
            © 2021 - El idrissi Chafik |
            <img
                    alt="Be Hance"
                    src="@/assets/images/icons/08_behance_t.png"
                />
                <img
                    alt="Dribbble"
                    src="@/assets/images/icons/04_dribbble_t.png"
                />
                <img
                    alt="LinkedIn"
                    src="@/assets/images/icons/07_linkedin_t.png"
                />
                <img
                    alt="Facebook"
                    src="@/assets/images/icons/02_facebook_t.png"
                />
                <img
                    alt="Instagram"
                    src="@/assets/images/icons/10_instagram_t.png"
                />
                <img
                    alt="Twitter"
                    src="@/assets/images/icons/01_twitter_t.png"
                />
        </div>
        <div class="col" id="footer_right">
            <div class="w-unset btn-round" id="footer_contact_btn">
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
    }
    #footer_right{
        max-width: fit-content;
        align-self: center;
    }
    #footer_left, #footer_contact_btn {
        font-size: 14px;
        font-weight: normal;
        color: #8D8D8E;
    }
    #footer_contact_btn{
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
