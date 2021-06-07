<template>
    <div class="row">
        <div class="row">
            <div id="project_filter">
              <div id="project_filter_all" @click="show('All')">Tous</div>
              <div id="project_filter_mobile" @click="filtering('Mobile')">Mobile</div>
              <div id="project_filter_web" @click="filtering('Web')">Web</div>
              <div id="project_filter_interaction" @click="filtering('Interaction')">Interaction</div>
            </div>
        </div>
        <div class="row">
            <div v-for="project in projects" :key="'project' + project.id"
                class="col-12 col-lg-4"
                :class="{ 'd-none' : !project.show }">
                <div class="card" @click="$emit('open-modal', 'project', projects[project.id - 1])">
                    <img
                        :src="require('@/assets/images/projects/' + project.src)"
                        class="card-img-top"
                        :alt="project.title">
                    <div class="card-body">
                        <p class="card-text" id="project_tags">
                            {{ project.subtitle }}
                        </p>
                        <h5 class="card-title" id="project_title">{{ project.title }}</h5>
                        <h5 class="card-title" id="project_year">{{ project.year }}</h5>
                    </div>
                </div>
            </div>
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
    filtering(name) { // Fontion de filtrage en fonction du tag
      this.hide(); // On cache tout
      // eslint-disable-next-line no-restricted-syntax
      for (const [index, value] of this.projects.entries()) {
        if ((value.tags).find((element) => element === name)) {
          this.show(index);
        }
      }
    },
    hide() { // Fonction de dissimulation de projets (filtrage)
      for (let i = 0; i < this.projects.length; i += 1) {
        this.projects[i].show = false;
      }
    },
    show(index) { // Fonction d'affichahe de projets (filtrage)
      for (let i = 0; i < this.projects.length; i += 1) {
        if (index === 'All') {
          this.projects[i].show = true; // On affiche tout
        } else if (this.projects[i].id === index + 1) this.projects[i].show = true; // On affiche l'index fournit
      }
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
    #project_filter{
      text-align: center;
    }
    #project_filter > div{
      display: inline-block;
      margin: 10px;
    }
    #project_tags{
      font-size: 12px;
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
