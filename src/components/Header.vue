<template>
  <header
    class="top_row"
    @scroll="scrollSticky"
    :class="{scrollStickyStyle:isScrollSticky}"
  >
    <div class="container">
      <div class="content">
        <h1 class="logo">
          <a class="logo_link" href="##">
            <img
              class="logo_img"
              src="https://evernote.com/img/logo/evernote/primary.svg"
              alt="evernote 品牌 logo"
            />
          </a>
        </h1>
        <div class="navbar">
          <nav class="navbar_introduction">
            <div class="navbar_introduction_list">
              <div>
                <a class="navbar_introduction_link" href="##">為什麼選擇 Evernote</a>
              </div>
              <div>
                <a class="navbar_introduction_link" href="##">
                  <span>功能</span>
                  <i class="fas fa-angle-down"></i>
                </a>
              </div>
              <div>
                <a class="navbar_introduction_link" href="##">
                  <span>方案</span>
                  <i class="fas fa-angle-down"></i>
                </a>
              </div>
            </div>
          </nav>
          <nav class="navbar_sign_in">
            <div class="navbar_sign_in_list">
              <div>
                <a class="navbar_sign_in_link" href="##">說明</a>
              </div>
              <div>
                <a class="navbar_sign_in_link" href="##">登入</a>
              </div>
              <div>
                <a
                  href="##"
                  class="navbar_sign_in_link navbar_sign_in_dm_download"
                >
                  下載
                </a>
              </div>
            </div>
          </nav>
        </div>
        <div class="navbar_btn_RWD">
          <img class="navbar_btn_img_RWD" src="https://evernote.com/img/icons/nav-open-tablet.svg" alt="打開導航列選單按鈕" @click="sidebarRwdShow">
        </div>
      </div>
    </div>
    <div class="sidebar_outer" :class="{sidebar_outer_RWD:isSidebarRwdStatus}"></div>
    <div class="sidebar" :class="{sidebar_rwd:isSidebarRwdStatus}">
      <div class="cross_img_outer">
        <img class="cross_img" src="https://evernote.com/img/icons/nav-close-tablet.svg" alt="關上導航列選單按鈕" @click="sidebarRwdClose">
      </div>
      <div>
        <div class="sidebar_list">
          <a class="sidebar_introduction_link" href="##">為什麼選擇 Evernote</a>
        </div>
        <div class="sidebar_list">
          <a class="sidebar_introduction_link" href="##">
            <span>功能</span>
            <i class="fas fa-angle-down"></i>
          </a>
        </div>
        <div class="sidebar_list">
          <a class="sidebar_introduction_link" href="##">
            <span>方案</span>
            <i class="fas fa-angle-down"></i>
          </a>
        </div>
        <div class="sidebar_list">
          <a class="sidebar_introduction_link" href="##">說明</a>
        </div>
        <div class="google_play">
          <a href="##" class="sidebar_dm_download_link">
            <img src="https://evernote.com/img/download/googleplay_badge_zh-tw.svg" alt="google play 立即下載圖片">
          </a>
        </div>
      </div>
    </div>
  </header>
</template>
<script>
export default {
  name: 'Header',
  data() {
    return {
      isScrollSticky: false,
      isSidebarRwdStatus: false,
    };
  },
  mounted() {
    this.windowScroll();
  },
  methods: {
    scrollSticky() {
      let scrollTop = document.documentElement.scrollTop || document.body.scrollTop;
      if (scrollTop > 55) {
        this.isScrollSticky = true;
        return;
      };

      this.isScrollSticky = false;
    },
    windowScroll() {
      window.addEventListener('scroll', this.scrollSticky);
    },
    sidebarRwdShow() {
      this.isSidebarRwdStatus = true;
      this.$emit('sidebarRwdFixed', this.isSidebarRwdStatus);
    },
    sidebarRwdClose() {
      this.isSidebarRwdStatus = false;
      this.$emit('sidebarRwdFixed', this.isSidebarRwdStatus);
    }
  },
};
</script>
<style scoped>
.top_row {
  width: 100%;
  background-color: white;
}
.scrollStickyStyle {
  position: fixed;
  border-bottom: 1px solid #f5fffa;
}
.content {
  display: flex;
  padding: 10px 35px;
}
.logo {
  width: 25%;
  height: 45px;
}
.logo_link {
  display: block;
  width: 100%;
  height: 100%;
}
.logo_img {
  width: 100%;
  height: 100%;
}
.navbar {
  display: flex;
  justify-content: space-between;
  width: 85%;
  height: 45px;
  line-height: 45px;
}
.navbar_introduction_list,
.navbar_sign_in_list {
  display: flex;
}
.navbar_introduction_link,
.navbar_sign_in_link,
.sidebar_introduction_link {
  padding: 5px 15px;
  color: black;
}
.navbar_introduction_link,
.sidebar_introduction_link {
  font-size: 0.7rem;
}
.navbar_sign_in_link {
  font-size: 0.9rem;
}
.navbar_sign_in_dm_download {
  padding: 5px 25px;
  border: 2px solid #00a82d;
  border-radius: 3px;
  color: #00a82d;
}
.navbar_btn_RWD {
  display: none;
}
.sidebar_outer {
  display: none;
}
.sidebar {
  display: none;
}
@media (max-width: 1200px) {
  .top_row .container{
    padding: 0;
  }
  .content {
    justify-content: space-between;
    padding: 15px 35px;
  }
  .logo {
    width: 35%;
    height: auto;
  }
  .navbar {
    display: none;
  }
  .navbar_btn_RWD {
    display: block;
    width: 5%;
    height: auto;
  }
  .navbar_btn_img_RWD {
    width: 100%;
    height: 100%;
  }
  .sidebar_outer_RWD {
    display: block;
    position: fixed;
    top: 0;
    left: 0;
    right: 0;
    bottom: 0;
    z-index: 2;
    background-color: black;
    opacity: 0.5;
  }
  .sidebar_rwd {
    display: block;
    width: 250px;
    position: fixed;
    top: 0;
    right: 0;
    bottom: 0;
    z-index: 3;
    padding: 25px;
    color: black;
    background-color: white;
  }
  .cross_img_outer {
    text-align: right;
  }
  .cross_img {
    width: 15px;
    height: 15px;
  }
  .sidebar_list {
    padding: 20px 5px;
    border-bottom: 1px solid#F2F2F2;
  }
  .navbar_introduction_link,
  .sidebar_introduction_link {
    padding: 5px 0;
    font-size: 1rem;
  }
  .google_play {
    text-align: center;
  }
  .sidebar_dm_download_link {
    display: inline-block;
    width: 55%;
    margin: 50px 0;
    text-align: center;
  }
}
@media (max-width: 550px) {
  .content {
    padding: 15px 15px;
  }
  .sidebar_rwd {
    width: auto;
    left: 0;
  }
  .logo {
    width: 45%;
    height: auto;
  }
}
</style>