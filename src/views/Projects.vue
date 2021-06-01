<template>
    <div class="row" v-on:click.tab.capture="closeModal($event)">
        <div class="row">
            <div id="project_filter">
              <div id="project_filter_all" @click="show('All')">Tous</div>
              <div id="project_filter_mobile" @click="filtering('Mobile')">Mobile</div>
              <div id="project_filter_web" @click="filtering('Web')">Web</div>
              <div id="project_filter_interaction" @click="filtering('Interaction')">
                Interaction</div>
            </div>
        </div>
        <div class="row">
            <div v-for="project in projects" :key="'project' + project.id"
                class="col col-xs-12 col-sm-12 col-md-4"
                :class="{ 'd-none' : !project.show }">
                <div class="card" @click="openModal(project.id - 1)">
                    <img
                        :src="require('@/assets/images/projects/' + project.src)"
                        class="card-img-top"
                        :alt="project.title">
                    <div class="card-body">
                        <p class="card-text">
                            {{ project.subtitle }}
                        </p>
                        <h5 class="card-title" id="project_title">{{ project.title }}</h5>
                        <h5 class="card-title" id="project_year">{{ project.year }}</h5>
                    </div>
                </div>
            </div>
        </div>

        <!-- Modal -->
        <div class="modal fade row"
          v-if="modal.show"
          :class="{ show : modal.show}"
          :style="{display: (modal.show && 'flex')|| 'none'}"
        >
          <div class="col-8" id="modal_left">
            <img
              :src="require('@/assets/images/projects/' + modal.src)"
              class="card-img-top"
              :alt="modal.title"
              >
          </div>
          <div class="col-4" id="modal_right">
            BLABLA
          </div>
        </div>

        <div class="modal-backdrop fade"
          v-if="modal.show"
          :class="{ show : modal.show}"
          :style="{ display : (modal.show && 'block')|| 'none'}"
          >
        </div>
    </div>
</template>

<script>

export default {
  name: 'Projects',
  data() {
    return {
      modal: {
        show: false,
        projectID: undefined,
        src: '',
        title: '',
      },
      filter: ['Mobile', 'Web', 'Interaction'],
      projects: [
        {
          id: 1,
          show: true,
          src: 'App-Screens-Perspective-MockUp-full.jpg',
          title: 'project title',
          subtitle: 'Web / Mobile',
          tags: ['Web', 'Mobile'],
          year: 2018,
        },
        {
          id: 2,
          show: true,
          src: 'sample_2.jpg',
          title: 'project title',
          tags: ['Interaction'],
          subtitle: 'Interaction',
          year: 2018,
        },
        {
          id: 3,
          show: true,
          src: 'sample_6.jpg',
          title: 'project title',
          tags: ['Web'],
          subtitle: 'Web',
          year: 2018,
        },
        {
          id: 4,
          show: true,
          src: 'sample_4.jpg',
          title: 'project title',
          tags: ['Web'],
          subtitle: 'Web',
          year: 2018,
        },
        {
          id: 5,
          show: true,
          src: 'sample_5.jpg',
          title: 'project title',
          tags: ['Mobile', 'Interaction'],
          subtitle: 'Mobile / Interaction',
          year: 2018,
        },
        {
          id: 6,
          show: true,
          src: 'sample_1.jpg',
          title: 'project title',
          tags: ['Interaction'],
          subtitle: 'Interaction',
          year: 2018,
        },
        {
          id: 7,
          show: true,
          src: 'sample_5.jpg',
          title: 'project title',
          tags: ['Mobile'],
          subtitle: 'Mobile',
          year: 2018,
        },
        {
          id: 8,
          show: true,
          src: 'Rectangle 405.jpg',
          title: 'project title',
          tags: ['Web', 'Mobile', 'Interaction'],
          subtitle: 'Web / Mobile / Interaction',
          year: 2018,
        },
        {
          id: 9,
          show: true,
          src: 'cover_photo.jpg',
          title: 'project title',
          tags: ['Interaction'],
          subtitle: 'Interaction',
          year: 2018,
        },
      ],
    };
  },
  methods: {
    filtering(name) {
      this.hide();
      // eslint-disable-next-line no-restricted-syntax
      for (const [index, value] of this.projects.entries()) {
        if ((value.tags).find((element) => element === name)) {
          this.show(index);
        }
      }
    },
    hide() {
      for (let i = 0; i < this.projects.length; i += 1) {
        this.projects[i].show = false;
      }
    },
    show(index) {
      for (let i = 0; i < this.projects.length; i += 1) {
        if (index === 'All') {
          this.projects[i].show = true;
        } else if (this.projects[i].id === index + 1) this.projects[i].show = true;
      }
    },
    openModal(index) {
      console.log('open');
      this.modal.projectID = index;
      this.modal.src = this.projects[index].src;
      this.modal.title = this.projects[index].tilte;
      this.modal.show = true;
    },
    closeModal(event) {
      console.log(event);
      if(event.)
      this.modal.show = false;
    },
  },
};
</script>

<style scoped>
    .card {
        margin: 25px;
    }
    .card:hover{
      transform: scale(1.05);
      box-shadow: 0 10px 20px rgba(0,0,0,.12), 0 4px 8px rgba(0,0,0,.06);
    }
    .modal{
      align-items: center;
    }
    #modal_right{
      background: white;
    }
    #project_filter{
      text-align: center;
    }
    #project_filter > div{
      display: inline-block;
      margin: 10px;
    }
    #project_title{
      float: left;
      text-transform: uppercase;
    }
    #project_year{
      float: right;
    }
    #project_title, #project_year{
      font-size: 20px;
      font-weight: bold;
    }
</style>
