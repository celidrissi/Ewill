<template>
  <Menu class="menu px-5" id="menu"/>
  <Me class="px-5 px-5" id="me"/>
  <Projects class="py-5 px-5" id="projects" @open-modal="openModal"/>
  <About class="py-5 px-5" id="about"/>
  <Modal id="modal"
    v-if="modal.show" :show="modal.show"
    @closeModal="closeModal"
    :type="modal.type" :object="modal.object"/>
  <Blog id="blog"/>
  <Footer class="px-5" id="footer"/>
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
      this.modal.type = type;
      this.modal.object = object;
      this.modal.show = true;
      // $('body').style.overflow = 'hidden'; // A debug
      document.getElementsByTagName('body')[0].style.overflow = 'hidden';
    },
    closeModal() {
      this.modal.show = false;
      this.modal.type = '';
      this.modal.object = {};
      // $('body').style.overflow = 'auto'; // A debug
      document.getElementsByTagName('body')[0].style.overflow = 'auto';
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
  }
  .menu {
    background-color: white;
    position: sticky;
    top: 0;
    z-index: 1;
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
    border-radius : 20px
  }
</style>
