<template>
  <div id="home-page" class="page-wrapper home-page">
    {/* prettier-ignore */}
    <!--    <site-hero-->
    <!--      :title="title"-->
    <!--      :subtitle="subtitle"-->
    <!--      :image="featureImage"-->
    <!--      style="margin:20px;"-->
    <!--    >-->
    <!--      &lt;!&ndash; <button-->
    <!--        class="button is-primary"-->
    <!--        @click="$eventBus.$emit('modal-triggered', 'newsletter-modal')"-->
    <!--      >-->
    <!--        Subscribe To Newsletter-->
    <!--      </button> &ndash;&gt;-->
    <!--    </site-hero>-->

    <div id="container">
      <!-- <img src="../assets/uploads/hero/1.jpg"-->
      <p style="font-size: 26pt;color: black;left: 50px;top:44.3%;">I do</p>
      <div
        style="background-image:url(http://imaging.nikon.com/lineup/dslr/df/img/sample/img_01.jpg);"
      >
        <p style="left:125px;">
          Landscape
        </p>
      </div>
      <div
        style="background-image:url(http://imaging.nikon.com/lineup/dslr/df/img/sample/img_02.jpg);"
      >
        <p style="left:85px;">
          Potrait
        </p>
      </div>
      <div
        style="background-image:url(http://imaging.nikon.com/lineup/dslr/df/img/sample/img_03.jpg);"
      >
        <p style="left:100px;">
          Wedding
        </p>
      </div>
      <div>
        <p style="color:black;left:130px;">
          Photography
        </p>
      </div>
    </div>
    <main-section theme="one-column">
      <template v-slot:default>
        <!-- All Posts -->
        <posts-grid />
      </template>
      <template v-slot:sidebar>
        Nothing here
      </template>
    </main-section>
    <!-- <news-letter-form-modal /> -->
  </div>
</template>

<script>
import { mapState } from 'vuex'
import { setPageData } from '../helper'
// import NewsLetterFormModal from '~/components/NewsLetterFormModal'

export default {
  name: 'HomePage',
  head() {
    return {
      title: `Home | ${this.$siteConfig.siteName}`
    }
  },
  // components: {
  //   // NewsLetterFormModal
  // },
  computed: {
    ...mapState(['title', 'subtitle', 'featureImage'])
  },
  fetch({ store, params }) {
    setPageData(store, { slug: 'home' })
  }
}
</script>

<style>
.home-page .under-subtitle {
  border-top: none;
}
</style>

<style scoped>
/* prettier-ignore */
#container {
  position:relative;
  height:700px;
  width:700px;
  left: 50%;
  top: 30%;
}
p {
  padding: 20px;
  font-size: 30pt;
  position: absolute;
  top: 30%;
  left: 13%;
  transform: translate(-50%, -50%);
  color: white;
}
#container div {
  position: absolute;
  margin: 100px;
  height: 100%;
  width: 100%;
  background-repeat: no-repeat;
  background-size: contain;
}
#container img {
  height: 70vh;
  width: 30vw;
}

@-webkit-keyframes imgFade {
  0% {
    opacity: 1;
  }
  17% {
    opacity: 1;
  }
  25% {
    opacity: 0;
  }
  92% {
    opacity: 0;
  }
  100% {
    opacity: 1;
  }
}

@-moz-keyframes imgFade {
  0% {
    opacity: 1;
  }
  17% {
    opacity: 1;
  }
  25% {
    opacity: 0;
  }
  92% {
    opacity: 0;
  }
  100% {
    opacity: 1;
  }
}

@-o-keyframes imgFade {
  0% {
    opacity: 1;
  }
  17% {
    opacity: 1;
  }
  25% {
    opacity: 0;
  }
  92% {
    opacity: 0;
  }
  100% {
    opacity: 1;
  }
}

@keyframes imgFade {
  0% {
    opacity: 1;
  }
  17% {
    opacity: 1;
  }
  25% {
    opacity: 0;
  }
  92% {
    opacity: 0;
  }
  100% {
    opacity: 1;
  }
}

#container div {
  -webkit-animation-name: imgFade;
  -webkit-animation-timing-function: ease-in-out;
  -webkit-animation-iteration-count: infinite;
  -webkit-animation-duration: 8s;

  -moz-animation-name: imgFade;
  -moz-animation-timing-function: ease-in-out;
  -moz-animation-iteration-count: infinite;
  -moz-animation-duration: 8s;

  -o-animation-name: imgFade;
  -o-animation-timing-function: ease-in-out;
  -o-animation-iteration-count: infinite;
  -o-animation-duration: 8s;

  animation-name: imgFade;
  animation-timing-function: ease-in-out;
  animation-iteration-count: infinite;
  animation-duration: 8s;
}
#container div:nth-of-type(1) {
  -webkit-animation-delay: 6s;
  -moz-animation-delay: 6s;
  -o-animation-delay: 6s;
  animation-delay: 6s;
}
#container div:nth-of-type(2) {
  -webkit-animation-delay: 4s;
  -moz-animation-delay: 4s;
  -o-animation-delay: 4s;
  animation-delay: 4s;
}
#container div:nth-of-type(3) {
  -webkit-animation-delay: 2s;
  -moz-animation-delay: 2s;
  -o-animation-delay: 2s;
  animation-delay: 2s;
}
#container div:nth-of-type(4) {
  -webkit-animation-delay: 0;
  -moz-animation-delay: 0;
  -o-animation-delay: 0;
  animation-delay: 0;
}
</style>
