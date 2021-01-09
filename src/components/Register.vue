<template>
  <div class="register">
    <div class="register_status">
      <h2 class="register_status_title">用 Evernote 完成更多事</h2>
      <p class="register_status_text">Evernote 能幫助您捕捉點子並快速找到。</p>
      <a class="register_status_sign_up" href="##">
        免費註冊
      </a>
    </div>
    <div class="register_summary">
      <div class="register_summary_img_outer">
        <img
          class="register_summary_img"
          src="https://evernote.com/c/assets/homepage/hp_hero_note@2x__en.png?5bb9868840cbc8b5"
          alt="圖片"
        />
      </div>
      <div class="register_summary_text">
        <div class="register_summary_text_list" v-for="(item,index) in registerSummaryList" :key="index">
          <p class="register_summary_text_title">{{item.title}}</p>
          <p class="register_summary_text_content">
            {{item.content}}
          </p>
        </div>
      </div>
      <div class="register_summary_text_RWD">
        <div class="register_summary_text_list" v-for="(item,index) in regsiterSummaryListFilter" :key="index">
          <p class="register_summary_text_title_RWD">{{item.title}}</p>
          <p class="regsiter_summary_text_descript_RWD">
            {{item.content}}
          </p>
        </div>
        <div class="dots">
          <div class="dot" v-for="(item, index) in registerSummaryList.length" :key="index" @click="changeTab(item)">
            <i class="fas fa-circle" :class="{fa_circle_color:item === currentTabId}"></i>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>
<script>
export default {
  name: 'Register',
  data() {
    return {
      registerSummaryList: [
        {
          id: 1,
          title: '隨處工作',
          content: '將您所有記事同步到所有裝置上，重要資料隨侍左右。',
        },
        {
          id: 2,
          title: '捕捉靈感資訊',
          content: '加更多文字、圖片、音檔、掃描檔、PDF 和文件到記事裡。',
        },
        {
          id: 3,
          title: '你的記事，隨你決定',
          content: '多樣的格式工具，讓您可以用自己的思考方式寫下自己的筆記。',
        },
        {
          id: 4,
          title: '快速資料查找',
          content: '最需要的時間，精準拿到需要的資料。您一邊輸入，Evernote 就開始提示搜尋結果。',
        },
      ],
      currentTabId: 1,
    };
  },
  mounted() {
    this.timer();
  },
  methods: {
    changeTab(item) {
      this.currentTabId = item;
    },
    timer() {
      return setInterval(() => {
        this.getData();
      },5000);
    },
    getData() {
      this.currentTabId +=1;
      if(this.currentTabId === this.registerSummaryList.length+1) {
        this.currentTabId = 1;
      };
    }
  },
  computed: {
    regsiterSummaryListFilter() {
      return this.registerSummaryList.filter( item => item.id === this.currentTabId);
    }
  }
};
</script>
<style scoped>
.register_status_title,
.register_status_text,
.register_status_sign_up {
  text-align: center;
}
.register_status_title {
  font-size: 3.5rem;
}
.register_status_text {
  font-size: 1.5rem;
}
.register_status_sign_up {
  display: block;
  width: 100px;
  padding: 15px 50px;
  margin: auto;
  border-radius: 5px;
  text-align: center;
  background: #00a82d;
  color: white;
}
.register_summary {
  display: flex;
  margin-top: 100px;
}
.register_summary_img_outer {
  width: 80%;
}
.register_summary_img {
  width: 100%;
}
.register_summary_text {
  width: 20%;
}
.register_summary_text_RWD {
  display: none;
}
.register_summary_text_list {
  padding: 0;
  margin: 25px 0;
}
main .register_summary_text_title {
  text-align: left;
  font-size: 1rem;
  font-weight: bold;
}
.register_summary_text_content {
  text-align: left;
  font-size: 0.3rem;
}
@media (max-width: 1200px) {
  .register {
    padding: 0 20px;
  }
  .register_status_title {
    font-size: 2.5rem;
  }
  .register_status_text {
    font-size: 1rem;
  }
}
@media (max-width: 770px) {
  .register {
    padding: 0 20px;
  }
  .register_status_text {
    font-size: 1rem;
  }
  .register_summary {
    flex-wrap: wrap;
  }
  .register_summary_img_outer,
  .register_summary_text {
    width: 100%;
  }
  .register_summary_text {
    display: none;
  }
  .register_summary_text_RWD {
    width: 100%;
    display: block;
    margin: 25px 0;
    text-align: center;
  }
  .register_summary_text_list {
    display: inline-block;
  }
  .register_summary_text_title_RWD {
    text-align: center;
    font-weight: bold;
  }
  .dot {
    display: inline-block;
    padding: 5px;
    margin: 0 15px;
  }
  .fa-circle {
    font-size: 0.1rem;
    color: gray;
  }
  .fa_circle_color {
    color: black;
  }
}
@media (max-width: 550px) {
  .register_status_title {
    font-size: 1.5rem;
  }
  .register_status_text {
    font-size: 0.8rem;
  }
  .register_status_sign_up {
    padding: 10px 10px;
  }
}
</style>