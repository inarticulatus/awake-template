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
    <div id="hero_text">
      <p>
        Hello!
        <br />
        I am <strong>Prakhar </strong>.
        <br />
        I love <strong> travelling </strong> and 
        <br />
        Photography
      </p>
    </div>
    <div id="container">
      <div>
              <img src="../assets/uploads/1.jpg" style="object-fit:cover;" />

      </div>
      <div>
       
        <img
          src="../assets/uploads/2.jpg"
          style="object-fit: cover;width: 700px;"
        />
      </div>
      <div>
       <img src="../assets/uploads/3.jpg" style="object-fit:cover;" />
      </div>
      <div>
        <p>
          <!-- style="left:81px;" -->
        </p>
        <img src="../assets/uploads/4.jpg" style="object-fit:cover;" />
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
@media screen and (min-width: 700px){
  #container {
    position:relative;
    height:738px;
    width:40vw;
    left: 50%;
    top: 30%;
  }
  p {
    padding: 0;
    padding-left: 10px;
    font-size: 26pt;
    position: relative;
    top: 445px;
    left: 50%;
    transform: translate(-50%, -50%);
    color: rgb(245, 245, 245);
  }
  #container div {
    position: absolute;
    margin: 61px;
    margin-top: 0px;
    height: 100%;
    width: 100%;
    background-repeat: no-repeat;
    object-fit: contain;
    /* background-size: contain; */
  }
  #container img {
    height: 77%;
    width: 100vw;
  }
  #hero_text p {
    top: 393px;
    left: 924px;
    color:grey;
  }
  #hero_text {
    height: 0;
  }
}

@media screen and (max-width: 700px) {
  .section {
    padding: 0rem 1.5rem;
  }
  #container {
    position: relative;
    height: 100vh;
    width: 100vw;
  }
  p {
    padding: 2px;
    font-size: 26pt;
    position: absolute;
    top: 377px;
    left: 51%;
    transform: translate(-50%, -50%);
    color: rgb(245, 245, 245);
    z-index: 1;
    text-align: center;
  }
  #container div {
    position: absolute;
    margin: 0px;
    padding: 10px;
    height: 100%;
    width: 100%;
    background-repeat: no-repeat;
    object-fit: contain;
    /* background-size: contain; */
  }
  #container img {
    height: 77%;
    width: 100vw;
  }
  #hero_text p {
    top: 286px;
    left: 50%;
    color: #4f4c4c;
    background-color: rgba(255, 255, 255, 0.5);
    height: 350px;
    width: 57vw;
  }
}

@media screen and (max-height: 600px) {
  #hero_text p {
    top: 50%;
  }
  p {
    padding: 2px;
    font-size: 26pt;
    position: absolute;
    top: 65%;
    left: 51%;
    transform: translate(-50%, -50%);
    color: rgb(245, 245, 245);
    z-index: 1;
    text-align: center;
  }
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
