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
      <p style="font-size: 26pt;color: black;left: 60px;top:75.3%;">
        I do
      </p>
      <div>
        <p style="left:108px;">
          Landscape
        </p>
        <img src="../assets/uploads/landscape.jpg" style="object-fit:cover;" />
      </div>
      <div>
        <p style="left:73px;">
          Potrait
        </p>
        <img src="../assets/uploads/potrait.jpg" style="object-fit:cover;" />
      </div>
      <div style="background-image: url(../assets/uploads/wedding.jpg);">
        <p style="left:90px;">
          Wedding
        </p>
        <img src="../assets/uploads/wedding.jpg" style="object-fit:cover;" />
      </div>
      <div style="background-color:white;">
        <p style="color:black;left:113px;font-size:26pt;">
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
  left: 30%;
  top: 30%;
}
p {
  padding: 20px;
  font-size: 30pt;
  position: absolute;
  top: 61%;
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
  object-fit: contain;
  /* background-size: contain; */
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
  -webkit-animation-duration: 16s;

  -moz-animation-name: imgFade;
  -moz-animation-timing-function: ease-in-out;
  -moz-animation-iteration-count: infinite;
  -moz-animation-duration: 16s;

  -o-animation-name: imgFade;
  -o-animation-timing-function: ease-in-out;
  -o-animation-iteration-count: infinite;
  -o-animation-duration: 16s;

  animation-name: imgFade;
  animation-timing-function: ease-in-out;
  animation-iteration-count: infinite;
  animation-duration: 16s;
}
#container div:nth-of-type(1) {
  -webkit-animation-delay: 12s;
  -moz-animation-delay: 12s;
  -o-animation-delay: 12s;
  animation-delay: 12s;
}
#container div:nth-of-type(2) {
  -webkit-animation-delay: 8s;
  -moz-animation-delay: 8s;
  -o-animation-delay: 8s;
  animation-delay: 8s;
}
#container div:nth-of-type(3) {
  -webkit-animation-delay: 4s;
  -moz-animation-delay: 4s;
  -o-animation-delay: 4s;
  animation-delay: 4s;
}
#container div:nth-of-type(4) {
  -webkit-animation-delay: 0;
  -moz-animation-delay: 0;
  -o-animation-delay: 0;
  animation-delay: 0;
}
</style>
