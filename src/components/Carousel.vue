<template>
  <div class="carousel">
    <div class="container clear_container_padding">
      <div class="carousel_text">
        <div class="carousel_content_quote">
          <img
            src="https://evernote.com/c/assets/homepage/homepage-quote.svg?8600d4c2697886e0"
            alt="引用符號"
          />
        </div>
        <div
          class="carousel_content_text_outer"
          v-for="(item, index) in carouselContentFilter"
          :key="index"
        >
          <p class="carousel_content_text">{{ item.content }}</p>
          <p class="carousel_content_text">— {{ item.author }}</p>
        </div>
      </div>
      <div class="carousel_alltabs">
        <a
          class="carousel_tab"
          v-for="(item, index) in carouselContent"
          :key="index"
          @click="changeTab(item)"
        >
          <img
            class="carousel_tab_img"
            :class="{changeTabStyle:currentCarouselContentId === item.id}"
            :src="item.tab_img"
            alt="品牌logo"
          />
        </a>
      </div>
      <div class="carousel_allTab_RWD">
        <div
          class="carousel_tab_RWD"
          v-for="(item, index) in carouselContentFilter"
          :key="index"
          @click="changeTab(item)"
        >
          <img
            class="carousel_tab_img_RWD"
            :class="{changeTabStyle:currentCarouselContentId === item.id}"
            :src="item.tab_img"
            alt="品牌logo"
          />
        </div>
        <div class="dots">
          <div class="dot" v-for="(item, index) in carouselContent.length" :key="index" @click="changeTab(item)">
            <i class="fas fa-circle" :class="{fa_circle_style:currentCarouselContentId === item}"></i>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>
<script>
export default {
  name: 'Carousel',
  data() {
    return {
      carouselContent: [
        {
          id: 1,
          content: '“Evernote 是套強大的工具，有助於高階管理人員、創業家、創意人捕捉並整理自己的點子。用就對了。”',
          author: 'Forbes',
          tab_img: 'https://evernote.com/c/assets/homepage/forbes-active.png?e6a09e3f0fb7d023'
        },
        {
          id: 2,
          content: '“Evernote 是個強大的工具，讓您可以同時管理工作任務和所需資料。”',
          author: 'Inc. Magazine',
          tab_img: 'https://evernote.com/c/assets/homepage/logo-inc-active.png?b9ce989daf7162c0'
        },
        {
          id: 3,
          content: '“似乎有無限種使用 Evernote 的方式...不論是用於學業、工作、生活、任何地方。”',
          author: 'The Verge',
          tab_img: 'https://evernote.com/c/assets/homepage/the-verge_active.png?919e4b051358b107'
        },
        {
          id: 4,
          content: '“多年前一次電腦故障的意外，讓我遺失所有儲存在電腦上的筆記。這讓我終於下定決心擁抱雲端，下載 Evernote。從此再也不回頭。”',
          author: 'Entrepreneur Magazine',
          tab_img: 'https://evernote.com/c/assets/homepage/entrepreneur-magazine_active.png?fb0bad786f125e9b'
        },
        {
          id: 5,
          content: '“您還可以直接轉寄電子郵件到 Evernote，將所有資訊全都集中一處。”',
          author: 'Business.com',
          tab_img: 'https://evernote.com/c/assets/homepage/business-active.png?5d947d289f675d42'
        },
        {
          id: 6,
          content: '“將 Evernote 當作不僅僅是儲存待辦清單，而是所有記事的集中站。Evernote 提供豐富多種的各種資料整理方式，而且所有資料都可以同步到每一個有支援的裝置上。生活不漏拍！”',
          author: 'Well + Good',
          tab_img: 'https://evernote.com/c/assets/homepage/well-good_active.png?6a4919b000325c2a'
        },
      ],
      currentCarouselContentId: 1,
    };
  },
  mounted() {
    this.timer();
  },
  methods: {
    changeTab(item) {
      // 因為carsouel 裡面有分成  不是rwd 和 rwd 呈現的畫面不一樣, 所以當 不是 rwd 的時候 會取 item.id; 所以當 是 rwd 的時候 會取 item
      // 有item.id 就會賦予給carouselContentId,item.id 為 undefind,就會用 ||,item 有值 會賦予給carouselContentId
      this.currentCarouselContentId = item.id || item;
    },
    timer() {
      return setInterval(() => {
        this.getData();
      }, 3000);
    },
    getData() {
      if (this.currentCarouselContentId === this.carouselContent.length) {
        this.currentCarouselContentId = 1;
        return
      }

      this.currentCarouselContentId += 1;
    },
  },
  computed: {
    carouselContentFilter() {
      return this.carouselContent.filter( item => item.id === this.currentCarouselContentId );
    },
  },
};
</script>
<style scoped>
/* carousel */
.clear_container_padding {
  padding: 0;
}
.carousel {
  padding: 50px 15px;
  background-color: #f8f8f8;
}
.carousel_text {
  height: 350px;
}
.carousel_content_quote {
  padding: 25px 0;
}
.carousel_content_text_outer {
  margin-bottom: 100px;
  padding: 0 50px;
}
.carousel_content_quote,
.carousel_content_text {
  text-align: center;
}
.carousel_content_text {
  margin: 0;
  line-height: 25px;
  font-size: 1.2rem;
}
.carousel_alltabs {
  display: flex;
  justify-content: space-between;
}
.carousel_tab {
  display: inline-block;
  width: 110px;
  height: auto;
  margin: 0 15px;
  cursor: pointer;
}
.carousel .changeTabStyle {
  opacity: 1;
}
.carousel_tab_img {
  width: 100%;
  height: 100%;
  opacity: 0.25;
}
.carousel_allTab_RWD {
  display: none;
}
@media (max-width: 600px) {
  .carousel_content_text_outer {
    margin-bottom: 0;
  }
  .carousel_text {
    height: 250px;
  }
  .carousel_content_text {
    font-size: 1rem;
  }
  .carousel_alltabs {
    display: none;
  }
  .carousel_allTab_RWD {
  display: block;
  }
  .dots {
    display: flex;
    justify-content: center;
  }
  .carousel_tab_RWD {
    width: 80px;
    height: 25px;
    margin: 25px auto;
    text-align: center;
  }
  .carousel_tab_img_RWD {
    width: 100%;
    height: 100%;
    opacity: 1;
  }
  .dot {
    padding: 5px;
    margin: 0 15px;
  }
  .fa-circle {
    font-size: 0.1rem;
    color: gray;
  }
  .fa_circle_style {
    color: black;
  }
}
@media (max-width: 300px) {
  .dot {
    padding: 0;
  }
  .carousel_content_text {
    font-size: 0.3rem;
  }
}
</style>
