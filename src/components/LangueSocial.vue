<template>
  <div class="langue_social">
    <div class="langue">
      <p class="langue_content">
        <span class="langue_text_optiones">Choose a language:</span>
        <span class="langue_text_option">中文（繁體）</span>
        <i class="fas fa-angle-down"></i>
      </p>
    </div>
    <hr class="line_bold">
    <div class="social">
      <a class="social_img_outer" href="##" v-for="(item, index) in socialImg" :key="index" >
        <img
          class="social_img"
          :src= item.img
          :alt= item.alt
        />
      </a>
    </div>
  </div>
</template>
<script>
export default {
  name: 'LangueSocial',
  data() {
    return {
      socialImg: [
        {
          id: 1,
          img: 'https://evernote.com/c/assets/social/facebook.svg?7202eb1971d2bae',
          alt: 'fb'
        },
        {
          id: 2,
          img: 'https://evernote.com/c/assets/social/twitter.svg?d25b8a0ce7fb98ef',
          alt: 'twitter'
        },
        {
          id: 3,
          img: 'https://evernote.com/c/assets/social/medium.svg?ba4b8caf9ab14358',
          alt: 'medium'
        },
        {
          id: 4,
          img: 'https://evernote.com/c/assets/social/instagram.svg?69cd249dce35a513',
          alt: 'instagram'
        },
        {
          id: 5,
          img: 'https://evernote.com/c/assets/social/youtube.svg?48fe9f27b8c63ade',
          alt: 'youtube'
        },
        {
          id: 6,
          img: 'https://evernote.com/c/assets/social/linkedin.svg?4c5617ce6d003552',
          alt: 'linkin'
        }
      ]
    }
  }
};
</script>
<style scoped>
.langue_social {
  display: flex;
  justify-content: space-between;
}
.line_bold {
  display: none;
  width: 100%;
  border-top: 3px solid black;
}
.langue_social {
  margin: 0;
}
.social a + a {
  margin-left: 15px;
}
.social_img_outer {
  display: inline-block;
  max-width: 35px;
  max-height: 35px;
}
.social_img {
  width: 100%;
  height: 100%;
}
@media (max-width: 600px) {
  .langue_social {
    flex-direction: column;
  }
  .line_bold {
    display: block;
    width: 100%;
    border-top: 3px solid black;
    order: -1;
  }
  .social {
    display: flex;
    justify-content: space-between;
    width: 100%;
    order: -2;
    margin-bottom: 50px;
  }
  .langue {
    padding: 50px 0;
  }
  .langue_content {
    display: flex;
  }
  .langue_text_option {
    order: 1;
    position: absolute;
    right: 20px;
  }
  .fa-angle-down {
    padding: 0 15px;
    font-size: 1.5rem;
  }
}
@media (max-width:300px) {
  .langue_content {
    font-size: 0.5rem;
  }
}
</style>