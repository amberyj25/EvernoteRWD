<template>
  <div class="guild">
    <ul class="footer_nav">
      <li
        class="footer_nav_content"
        v-for="(footerNav, index) in footerNavs"
        :key="index"
      >
        <h6>{{ footerNav.title }}</h6>
        <ul class="footer_subnav_content">
          <li
            class="footer_subnav_content"
            v-for="(list, index) in footerNav.content"
            :key="index"
          >
            {{ list }}
          </li>
        </ul>
      </li>
    </ul>
  </div>
</template>
<script>
export default {
  name: 'Guild',
  data() {
    return {
      footerNavs: [
        {
          title: '產品',
          content: [
            '為什麼選擇 Evernote',
            'Evernote 入門版',
            'Evernote 專業版',
            'Evernote 企業版',
            '方案比較',
            '學生優惠',
            '下載應用程式',
          ],
        },
        {
          title: '功能',
          content: [
            'Web Clipper',
            '範本',
            'Space',
            '整合',
            '記事同步處理',
            'PDF 檔和文件搜尋',
            '搜尋手寫文字',
            '文件掃描',
            '記事本 & 標籤',
          ],
        },
        {
          title: '社群',
          content: [
            'Evernote 社群',
            '認證顧問',
            'Beta 計畫',
            '開發人員',
            '活動',
            '論壇',
          ],
        },
        {
          title: '支援',
          content: ['支援 & 學習中心', '疑難排解', '部落格'],
        },
        {
          title: '公司',
          content: ['關於我們', '人才招募', '聯絡我們'],
        },
      ],
    };
  },
};
</script>
<style scoped>
.footer_nav {
  display: flex;
  justify-content: space-between;
  width: 75%;
}
.footer_nav_content {
  margin-top: 25px;
  font-size: 1rem;
}
.footer_subnav_content {
  margin: 25px 0;
  font-size: 0.7rem;
}
@media (max-width: 600px) {
  .footer_nav {
    display: block;
  }
  .footer_nav_content {
    margin: 58px 0;
    font-size: 1.5rem;
  }
  .footer_subnav_content {
    font-size: 0.7rem;
  }
}
</style>