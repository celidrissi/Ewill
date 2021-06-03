<template>
    <div class="row">
        <div class="col-xs-12 col-sm-12 col-md-6" id="about_left_pane">
            <img src="@/assets/images/undraw_Designer_by46.svg" alt="Designer Image">
        </div>
        <div class="col-xs-12 col-sm-12 col-md-6" id="about_right_pane">
            <p id="about_title">
                à propos...
            </p>
            <p id="about_subtitle">
                qui suis-je ?
            </p>
            <p id="about_text">
                Lorem ipsum dolor sit amet, consectetur adipiscing elit.
                Maecenas pellentesque eu enim eget luctus. Sed augue felis,
                facilisis et elementum vitae, aliquam sit amet ante. Sed iaculis
                eros sem, elementum consequat est consequat eu. Quisque
                aliquet a ipsum nec tincidunt. Nulla vitae rhoncus leo. Praesent
                dui sapien, bibendum quis tempus dictum, auctor ac dui.
                Vestibulum ante ipsum primis in faucibus orci luctus et ultrices
                posuere cubilia Curae; Donec at mauris porta, ullamcorper sem
                quis, lobortis sem. Donec sit amet aliquet dui, at varius est.
                Phasellus porttitor finibus neque vel vehicula.
            </p>
            <div id="about_contact">
                <div class="w-unset btn-round" id="about_contact_btn" @click="$emit('open-modal', 'contact')">
                    CONTACT
                </div>
            </div>
        </div>
    </div>
</template>

<script>

export default {
  name: 'About',
};
</script>

<style scoped>
    #about_left_pane > img {
        width: 100%;
    }
    #about_title {
        font-size: 45px;
        font-weight: bold;
        text-transform: uppercase;
    }
    #about_subtitle {
        font-size: 72px;
        font-weight: bold;
        opacity: 15%;
        text-transform: uppercase;
    }
    #about_text {
        font-size: 15px;
        font-weight: lighter;
        inline-size: 74%;
        color: #6A696B;
    }
    #about_contact{
        max-width: fit-content;
    }
    #about_contact_btn{
        padding-left: 45px;
        padding-right: 45px;
        padding-top: 5px;
        padding-bottom: 5px;
        border-color: #8D8D8E;
    }
    #about_contact_btn:hover {
        background: #2B2A2C;
        color: #8D8D8E;
    }
</style>
