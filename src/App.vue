<template>
  <Menu class="menu px-15" id="menu" @open-modal="openModal"/>
  <Me class="py-5 px-15" id="me" @open-modal="openModal"/>
  <Projects class="py-5 px-15" id="projects" @open-modal="openModal"/>
  <About class="py-5 px-15" id="about" @open-modal="openModal"/>
  <Modal id="modal" v-if="modal.show" :show="modal.show" @closeModal="closeModal" :type="modal.type" :object="modal.object" :overflow="modal.show && 'auto' || 'hidden'"/>
  <Blog id="blog"/>
  <Footer class="px-15" id="footer" @open-modal="openModal"/>
</template>

<script>
// import $ from 'jquery'; A debug

import Menu from '@/views/Menu.vue';
import Me from '@/views/Me.vue';
import Projects from '@/views/Projects.vue';
import About from '@/views/About.vue';
import Modal from '@/views/Modal.vue';
import Footer from '@/views/Footer.vue';
import Blog from '@/views/Blog.vue';

export default {
  name: 'Main',
  data() {
    return {
      modal: {
        show: false,
        type: '',
        object: {},
      },
    };
  },
  components: {
    Menu,
    Me,
    Projects,
    About,
    Modal,
    Footer,
    Blog,
  },
  methods: {
    openModal(type, object) {
      this.modal.type = type; // Setup du type de modal
      if (this.modal.object !== undefined) this.modal.object = object; // Modal de type 'Contact'
      if (this.modal.type === 'project') this.modal.object.src = 'popup-2.jpg'; // Modal de type 'Projet'
      // A noter : Pour la ligne Supérieure, 'popup-2.jpg' peut etre remplacé par object.src pour avoir l'image du projet
      this.modal.show = true;
    },
    closeModal() {
      // RAZ du modal;
      this.modal.show = false;
      this.modal.type = '';
      this.modal.object = {};
    },
  },
};

</script>

<style>
  * {
    font-family: 'Montserrat', sans-serif;
    color: #2B2A2C;
  }
  body {
    overflow: auto;
    width: fit-content;
  }
  .menu {
    background-color: white;
    position: sticky;
    top: 0;
    z-index: 1;
    box-shadow: 0px 5px 10px lightgrey;
    padding-bottom: 1em;
  }
  .modal {
    margin: auto;
    bottom: 0;
    right: 0;
    justify-content: center;
  }
  .px-10 {
    padding-right: 6rem !important;
    padding-left: 6rem !important;
  }
  .px-15 {
    padding-right: 9rem !important;
    padding-left: 9rem !important;
  }
  .py-10 {
    padding-top: 6rem !important;
    padding-bottom: 6rem !important;
  }
  .py-15 {
    padding-top: 9rem !important;
    padding-bottom: 9rem !important;
  }
  .btn-round{
    border : 2px solid black;
    border-radius : 30px;
  }
</style>
