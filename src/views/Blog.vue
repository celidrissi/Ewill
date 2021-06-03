<template>
    <div class="row">
      <div class="row" id="blog_top">
        Lorem ipsum dolor sit amet, consectetur adipiscing elit. Maecenas
        pellentesque eu enim eget luctus. Sed augue felis, facilisis et
        elementum vitae, aliquam sit amet ante. Sed iaculis eros sem, elementum
        consequat est consequat eu. Quisque aliquet a ipsum nec tincidunt.
        Nulla vitae rhoncus leo. Praesent dui sapien, bibendum quis tempus dictum.
      </div>
      <div class="row" id="blog_user">
        <div id="blog_user_photo">
            <img
            class="rounded-circle rounded-photo"
            alt="USer Photo"
            src="@/assets/images/lena.jpg"/>
        </div>
        <div id="blog_user_info">
            <div class="col-12" id="blog_user_fullname">Lena M. Brooks</div>
            <div class="col-12" id="blog_user_job">Marketing House</div>
        </div>
      </div>
      <div class="row py-10" id="blog_content">
        <div class="col-12" id="blog_content_title">
          MON BLOG
        </div>
        <div class="col-12 mb-5" id="blog_content_subtitle">
          Mes avis sur les dernieres tendances du Web
        </div>
        <div class="row px-15">
          <div v-for="article in articles" :key="'article' + article.id"
            class="col col-xs-12 col-sm-12 col-md-4"
            id="blog_content_items">
            <div class="card">
              <div id="card_date">
                <h5>{{ article.day }}</h5>
                <h5>{{ article.month }}</h5>
              </div>
              <img
                :src="require('@/assets/images/blog/' + article.src)"
                class="card-img-top"
                :alt="article.title">
              <div class="card-body">
                <h5 class="card-title">{{ article.title }}</h5>
                <p class="card-text">
                    {{ article.subtitle }}
                </p>
                <div class="btn-round" id="article_read">
                    LIRE
                </div>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
</template>

<script>

export default {
  name: 'Blog',
  data() {
    return {
      stars: 4.5,
      articles: [
        {
          id: 1,
          day: 10,
          month: 'JAN',
          src: 'airbnb-2384737_1920.jpg',
          title: 'TEN THE BEST APP IN 2017',
          subtitle: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit. Maecenas pellentesque eu enim eget luctus. Sed augue felis, facilisis et elementum vitae, aliquam sit amet ante. Sed iaculis eros sem, elementum consequat.',
        },
        {
          id: 2,
          day: 15,
          month: 'JAN',
          src: 'office-820390_1920.jpg',
          title: 'WEBSITE INSPIRATION',
          subtitle: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit. Maecenas pellentesque eu enim eget luctus. Sed augue felis, facilisis et elementum vitae, aliquam sit amet ante. Sed iaculis eros sem, elementum consequat.',
        },
        {
          id: 3,
          day: 10,
          month: 'JAN',
          src: 'technology-3164715_1920.jpg',
          title: 'CHANGES IN SOCIAL MEDIA',
          subtitle: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit. Maecenas pellentesque eu enim eget luctus. Sed augue felis, facilisis et elementum vitae, aliquam sit amet ante. Sed iaculis eros sem, elementum consequat.',
        },
      ],
    };
  },
};
</script>

<style scoped>
  #blog_top{
    background-color:#2B2A2C;
    font-size: 18px;
    font-weight: normal;
    color: #8D8D8E;
    text-align: center;
    padding-right: 300px !important;
    padding-left: 300px !important;
    padding-top: 50px;
    padding-bottom: 50px;
  }
  #blog_user {
    text-align: center;
    margin-top: -40px;
  }
  #blog_user_photo > img{
    width: 170px;
    border: 4px solid white;
  }
  #blog_content_title, #blog_content_subtitle {
    text-align: center;
  }
  #blog_content_title {
    font-size: 45px;
    font-weight: bold;
  }
  #blog_content_subtitle {
    font-size: 18px;
    font-weight: normal;
    color: #8C8C8D;
  }
  #card_date{
    background-color: #2B2A2C;
    color: #8D8D8E;
    position: absolute;
    width: 77px;
    height: 77px;
    padding: 10px;
  }
  #card_date > * {
    color: #8D8D8E;
    text-align: center;
    margin: 0;
  }
  #article_read{
    max-width: fit-content;
    padding-left: 45px;
    padding-right: 45px;
    padding-top: 5px;
    padding-bottom: 5px;
  }
  #article_read:hover {
    background: #2B2A2C;
    color: #8D8D8E;
  }
</style>
