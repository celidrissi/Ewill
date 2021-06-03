<template>
  <div>
    <div class="modal fade row show" :style="{display: (show && 'flex')|| 'none'}">
        <img
            :src="require('@/assets/images/projects/' + object.src)"
            class="col-8" id="modal_left"
            :alt="object.title"
            @click="getModalRightH"
            @load="setH()"
            >
        <div class="col-4 row" id="modal_right">
          <div class="row-1">
            <img id="modal_close"
              :src="require('@/assets/images/icons/002-close.png')" alt="Close Button">
          </div>
          <div id="modal">
            BLABLA
          </div>
        </div>
    </div>
    <div class="modal-backdrop fade show" :style="{ display : (show && 'block')|| 'none'}"
      v-on:click="$emit('close-modal')"/>
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
      console.log(imgH);
      document.getElementById('modal_right').style.height = `${imgH}px`;
    },
  },
};
</script>

<style scoped>
    .modal{
      align-items: center;
      max-width: 100%;
      height: fit-content;
    }
    #modal_left{
      height: 100%;
      padding: 0;
      max-width: 60%;
    }
    #modal_right{
      background: red;
      height: 100%;
      margin: 0;
    }
    #modal_close{
      height: 44px;
    }
</style>
