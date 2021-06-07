<template>
  <div class="modal fade row show" :style="{display: (show && 'flex')|| 'none'}">
    <template v-if="type === 'project'">
      <img class="col-12 col-md-6" id="modal_left" :src="require('@/assets/images/' + object.src)" :alt="object.title" @load="setH()">
      <div class="col-12 col-md-6 px-4" id="modal_right">
        <div id="modal_right_top">
          <img id="modal_close" @click="$emit('close-modal')" :src="require('@/assets/images/icons/002-close.png')" alt="Close Button">
        </div>
        <div id="modal_right_bottom">
          <div id="project_name">NOM DU PROJET</div>
          <div id="project_info">
            <div id="project_info_category">CATEGORY</div> | <div id="project_info_year">2018</div>
          </div>
          <div class="py-3" id="project_client_info">
            <div id="project_client_info_label">Client :</div>
            <div id="project_client_info_name">Creative Agency</div>
          </div>
          <p id="project_text">
            Lorem ipsum dolor sit amet, consectetur adipiscing elit. Maecenas pellentesque eu enim eget luctus.
            Sed augue felis, facilisis et elementum vitae, aliquam sit amet ante. Sed iaculis eros sem, elementum
            consequat est consequat eu. Quisque aliquet a ipsum nec tincidunt. Nulla vitae rhoncus leo. Praesent
            dui sapien, bibendum quis tempus dictum, auctor ac dui. Vestibulum ante ipsum primis in faucibus orci
            luctus et ultrices posuere cubilia Curae; Donec at mauris porta, ullamcorper sem quis, lobortis sem.
            Donec sit amet aliquet dui, at varius est. Phasellus porttitor finibus neque vel vehicula. Duis in
            nulla egestas, dignissim elit at, imperdiet eros. Integer tristique posuere purus. Suspendisse placerat,
            quam vitae ullamcorper
          </p>
        </div>
      </div>
    </template>
    <template v-if="type === 'contact'">
      <div class="col-11 col-lg-6 px-4" id="modal_right">
        <div id="modal_right_bottom">
          <div class="py-3" id="contact_title">
            Contact
            <div id="contact_subtitle">Appelez-moi ou envoyer-moi un mail</div>
          </div>
          <div class="py-3" id="contact_info">
            <div id="contact_phone">01 02 03 04 05</div>
            <div id="contact_adress">designer@ui43.com</div>
          </div>
          <div id="contact_mail">
            <div id="contact_from">
              Adresse e-mail <br/>
              <input type="text" placeholder="Adresse e-mail"/>
            </div>
            <div id="contact_content">
              Contenu <br/>
              <input type="text" placeholder="Contenu"/>
            </div>
          </div>
          <div id="contact_send">
            <div id="contact_send_button" class="w-unset btn-round"> CONTACT </div>
          </div>
        </div>
      </div>
      <div class="col-1 col-lg-4" id="modal_right">
        <img id="modal_close_contact" class="d-flex d-lg-none" @click="$emit('close-modal')" :src="require('@/assets/images/icons/002-close.png')" alt="Close Button">
        <img id="modal_close_contact" class="d-none d-lg-flex t_white" @click="$emit('close-modal')" :src="require('@/assets/images/icons/002-close.png')" alt="Close Button">
        <img class="col-8 d-none d-lg-block" id="modal_right_contact" @load="setH()" :src="require('@/assets/images/popup-1.jpg')" alt="Contact Image">
      </div>
    </template>
  </div>
  <div class="modal-backdrop fade show" :style="{ display : (show && 'block')|| 'none'}" v-on:click="$emit('close-modal')"/>
</template>

<script>

export default {
  name: 'Modal',
  props: {
    show: Boolean,
    type: String,
    object: Object,
  },
};
</script>

<style scoped>
    input {
      width: 100%;
      border: 1px solid lightgrey;
      border-radius: 31px;
    }
    input::placeholder {
      color: #2B2A2C;
    }
    input[type="text"] {
      padding: 20px 10px;
      line-height: 28px;
    }
    .modal{
      max-width: 100%;
      height: 100%;
    }
    .modal-backdrop {
      background-color: white;
      opacity: 1;
    }
    .t_white{
      filter: invert(100%);
    }
    #modal_left{
      margin-top: 0;
      padding: 0;
    }
    #modal_right{
      background: white;
      margin: 0;
    }
    #modal_right_contact{
      background: white;
      height: 100%;
      padding: 0;
      margin: 0;
      width: auto;
    }
    #modal_close{
      height: 44px;
      float: right;
    }
    #modal_close_contact{
      height: 44px;
      float: right;
      width: auto;
      position: absolute;
      top: calc(var(--bs-gutter-x));
      right: calc(var(--bs-gutter-x)*1);
    }
    #modal_right_top{
      position: absolute;
      top: 0;
      right: 0;
      padding: calc(var(--bs-gutter-x) / 2);
    }
    #modal_right_bottom {
      height: 100%
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
      inline-size:9 0%;
      text-overflow: ellipsis;
      overflow: hidden;
      position: relative;
      max-height: 22.5em;
    }
    #contact_title{
      font-size: 45px;
      font-weight: bold;
      text-transform: uppercase;
    }
    #contact_subtitle{
      font-size: 16px;
      font-weight: bold;
      text-transform: uppercase;
    }
    #contact_phone{
      font-size: 14px;
      font-weight: bolder;
    }
    #contact_adress{
      font-size: 14px;
      font-weight: bolder;
    }
    #contact_mail {
      font-size: 16px;
      font-weight: bold;
    }
    #contact_from > input{
      height: 5vh;
    }
    #contact_content > input{
      height: 50vh;
    }
    #contact_send{
      font-size: 16px;
      font-weight: normal;
      text-transform: uppercase;
      width: 100%;
      position: relative;
    }
    #contact_send_button{
      padding-left: 45px;
      padding-right: 45px;
      padding-top: 10px;
      padding-bottom: 10px;
      margin-top: 20px;
      width: fit-content;
      position: absolute;
      right: 0;
    }
    #contact_send_button:hover {
      background: #2B2A2C;
      color: #8D8D8E;
    }
</style>
