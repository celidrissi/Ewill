<template>
    <div class="row">
        <div class="col-12 col-xs-12 col-sm-12 col-md-6" id="me_left_pane">
            <div class="row" id="me_txt">
                Hello, je suis...
            </div>
            <div class="row" id="me_name">
                Lewis Nathaniel
            </div>
            <div class="row" id="me_job">
                UI & UX Designer
            </div>
            <div class="row" id="me_social">
                <div class="col" id="me_social_icon">
                    <img
                        alt="Be Hance"
                        src="@/assets/images/icons/08_behance.png"
                    />
                    <img
                        alt="Dribbble"
                        src="@/assets/images/icons/04_dribbble.png"
                    />
                    <img
                        alt="LinkedIn"
                        src="@/assets/images/icons/07_linkedin.png"
                    />
                    <img
                        alt="Facebook"
                        src="@/assets/images/icons/02_facebook.png"
                    />
                    <img
                        alt="Instagram"
                        src="@/assets/images/icons/10_instagram.png"
                    />
                    <img
                        alt="Twitter"
                        src="@/assets/images/icons/01_twitter.png"
                    />
                </div>
            </div>
            <div id="me_contact">
                <div class="w-unset btn-round" id="me_contact_btn" @click="$emit('open-modal', 'contact')">
                    CONTACT
                </div>
            </div>
        </div>
        <div class="col-12 col-xs-12 col-sm-12 col-md-6" id="me_right_pane">
            <img
                alt="Designer Image"
                src="@/assets/images/undraw_innovative_b409.svg"
            />
        </div>
    </div>
</template>

<script>

export default {
  name: 'Me',
};
</script>

<style scoped>
    #me_txt {
        font-size: 32px;
        font-weight: lighter;
    }
    #me_name {
        font-size: 45px;
        font-weight: bold;
    }
    #me_job {
        font-size: 18px;
        font-weight: normal;
    }
    #me_social {
        padding-top: 10px;
        padding-bottom: 10px;
    }
    #me_social_icon {
        padding: unset;
    }
    #me_social_icon > img {
        margin-top: 10px;
        margin-right: 5px;
        margin-bottom: 10px;
    }
    #me_contact {
        padding-bottom: 20px;
    }
    #me_contact_btn {
        width: fit-content;
        padding-left: 30px;
        padding-right: 30px;
        padding-top: 5px;
        padding-bottom: 5px;
    }
    #me_contact_btn:hover {
        background: #2B2A2C;
        color: #8D8D8E;
    }
    #me_right_pane {
        text-align: right;
    }
    #me_right_pane > img {
        width: 100%;
    }
</style>
