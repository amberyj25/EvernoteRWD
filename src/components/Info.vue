<template>
  <div class="info">
    <div class="container">
      <div class="info_outer">
        <div v-for="(item, index) in infoContent" :key="index">
          <div class="info_odd">
            <div class="info_left">
              <img class="icon" :src="item.odd_icon" alt="圖片" />
              <h4 class="info_title">{{ item.odd_title }}</h4>
              <p class="info_content">{{ item.odd_content }}</p>
              <a class="info_odd_link" href="##">了解更多 →</a>
            </div>
            <div class="info_right">
              <img class="info_img" :src="item.odd_img" alt="圖片" />
            </div>
          </div>
          <div class="info_even">
            <div class="info_left">
              <img class="info_img" :src="item.even_img" alt="圖片" />
            </div>
            <div class="info_right order">
              <img class="icon" :src="item.even_icon" alt="圖片" />
              <h4 class="info_title">{{ item.even_title }}</h4>
              <p class="info_content">{{ item.even_content }}</p>
              <a class="info_even_link" href="##">了解更多 →</a>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>
<script>
export default {
  name: 'Info',
  data() {
    return {
      infoContent: [
        {
          odd_icon: 'https://evernote.com/c/assets/homepage/integrations.svg?aa993ea8778d4e5b',
          odd_title: '應用程式整合服務',
          odd_content: '跨應用程式分享內容。Evernote 可與多個熱門生產力工具連結，讓您用自己最習慣的工具達成最終目標。',
          odd_img: 'https://evernote.com/c/assets/homepage/feature_integration@2x.png?1adc1edb4f047984',
          even_icon: 'https://evernote.com/c/assets/homepage/doc-scanning.svg?c297fda085440f6d',
          even_title: '文件掃描',
          even_content: '邁向無紙化，將重要文件備份到您所有裝置上。保留真正重要的資訊而非雜物。',
          even_img: 'https://evernote.com/c/assets/homepage/feature_document_scanning_@2x__en.png?99f190b31999d220'
        },
        {
          odd_icon: 'https://evernote.com/c/assets/homepage/web-clipping.svg?f9a497087e4c09df',
          odd_title: 'Web Clipper',
          odd_content: '儲存網頁內容（去除廣告），還可再使用箭頭、螢光筆和文字標示重點。',
          odd_img: 'https://evernote.com/c/assets/homepage/feature_web_clipper_@2x__en.png?b975cb7529b8eb00',
          even_icon: 'https://evernote.com/c/assets/homepage/rich_notes.svg?48ba40a9369a4199',
          even_title: '文件掃描',
          even_content: '邁向無紙化，將重要文件備份到您所有裝置上。保留真正重要的資訊而非雜物。',
          even_img: 'https://evernote.com/c/assets/homepage/feature_mobile_@2x__en.png?316e3505a2111adb'
        },
      ],
    };
  },
};
</script>
<style scoped>
.info_outer {
  margin: 100px 0;
}
.info_odd,
.info_even {
  display: flex;
  justify-content: space-between;
  margin-bottom: 25px;
}
.info_odd_link,
.info_even_link {
  font-size: 0.8rem;
  color: #00a82d;
}
.info_left,
.info_right {
  width: 40%;
}
.icon {
  display: block;
  width: 55px;
  height: 55px;
}
.info_title {
  margin: 15px 0;
  font-size: 2rem;
  font-weight: lighter;
}
.info_content {
  font-size: 1.2rem;
  font-weight: lighter;
}
.info_img {
  width: 100%;
}
@media (max-width:1200px) {
  .info_outer {
    padding: 0 25px;
    margin: 50px 0;
  }
  .info_odd,
  .info_even {
    margin-bottom: 100px;
  }
}
@media (max-width:600px) {
  .info_odd,
  .info_even {
    flex-wrap: wrap;
    margin-bottom: 35px;
  }
  .info_left,
  .info_right {
    width: 100%;
    margin: 25px 0;
  }
  .order {
    order: -1;
  }
}
</style>