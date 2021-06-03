<template>
  <div>
    <div class="modal fade row show" :style="{display: (show && 'flex')|| 'none'}">
        <img :src="require('@/assets/images/' + object.src)" class="col-8" id="modal_left" :alt="object.title" @click="getModalRightH" @load="setH()">
        <div class="col-4 px-4" id="modal_right">
          <div id="modal_right_top">
            <img id="modal_close" @click="$emit('close-modal')" :src="require('@/assets/images/icons/002-close.png')" alt="Close Button">
          </div>
          <div id="modal_right_bottom">
            <template v-if="type === 'project'">
              <div id="project_name">NOM DU PROJET</div>
              <div id="project_info">
                <div id="project_info_category">CATEGORY</div> | <div id="project_info_year">2018</div>
              </div>
              <div class="py-5" id="project_client_info">
                <div id="project_client_info_label">Client :</div>
                <div id="project_client_info_name">Creative Agency</div>
              </div>
              <div id="project_text">
                Lorem ipsum dolor sit amet, consectetur adipiscing elit. Maecenas pellentesque eu enim eget luctus.
                Sed augue felis, facilisis et elementum vitae, aliquam sit amet ante. Sed iaculis eros sem, elementum
                consequat est consequat eu. Quisque aliquet a ipsum nec tincidunt. Nulla vitae rhoncus leo. Praesent
                dui sapien, bibendum quis tempus dictum, auctor ac dui. Vestibulum ante ipsum primis in faucibus orci
                luctus et ultrices posuere cubilia Curae; Donec at mauris porta, ullamcorper sem quis, lobortis sem.
                Donec sit amet aliquet dui, at varius est. Phasellus porttitor finibus neque vel vehicula. Duis in
                nulla egestas, dignissim elit at, imperdiet eros. Integer tristique posuere purus. Suspendisse placerat,
                quam vitae ullamcorper sollicitudin, dui ligula molestie massa, sit amet laoreet nibh ex vitae dui.
                Aenean laoreet pellentesque lacus, eget varius massa mattis quis. Nunc ultrices urna eu nunc lobortis
                pulvinar. Duis viverra, quam non imperdiet scelerisque, urna nunc consequat velit, in mollis erat nibh in libero.
              </div>
            </template>
            <template v-if="type === 'contact'">
              <div id="contact_title">Contact</div>
              <div id="contact_subtitle">Appelez-moi ou envoyer-moi un mail</div>
              <div id="contact_phone">01 02 03 04 05</div>
              <div id="contact_adress">designer@ui43.com</div>
              <div id="contact_mail">
                <div id="contact_from">Adresse e-mail</div>
                <div id="contact_content">Contenu</div>
              </div>
              <div id="contact_send">
                <div class="col w-unset btn-round" id="menu_contact">
                    CONTACT
                </div>
              </div>
            </template>
          </div>
        </div>
    </div>
    <div class="modal-backdrop fade show" :style="{ display : (show && 'block')|| 'none'}" v-on:click="$emit('close-modal')"/>
  </div>
</template>
<script>

export default {
  name: 'Modal',
  props: {
    show: Boolean,
    type: String,
    object: Object,
  },
  methods: {
    setH() {
      const imgH = document.getElementById('modal_left').height;
      document.getElementById('modal_right').style.height = `${imgH}px`;
    },
  },
};
</script>

<style scoped>
    .modal{
      align-items: center;
      max-width: 100%;
      height: 100%;
    }
    #modal_left{
      height: 100%;
      padding: 0;
      max-width: 60%;
    }
    #modal_right{
      background: white;
      height: 100%;
      margin: 0;
    }
    #modal_close{
      height: 44px;
      float: right;
    }
    #modal_right_top{
      height: fit-content;
      width: 100%;
      padding: calc(var(--bs-gutter-x) / 2);
    }
    #modal_right_bottom {

    }
    #project_name {
      font-size: 32px;
      font-weight: bold;
      color: #2B2A2C;
    }
    #project_info {
      display: inline-block;
    }
    #project_info_category {
      display: inline-block;
      font-size: 18px;
      font-weight: normal;
      color: #6A696B;
    }
    #project_info_year {
      display: inline-block;
      font-size: 18px;
      font-weight: normal;
      color: #6A696B;
    }
    #project_client_info_label {
      font-size: 24px;
      font-weight: bold;
      color: #2B2A2C;
    }
    #project_client_info_name {
      font-size: 22px;
      font-weight: italic;
    }
    #project_text {
      font-size: 18px;
      font-weight: bold;
      color: #6A696B;
      inline-size: 74%;
    }
</style>
