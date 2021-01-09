<template>
  <footer class="bottom_row">
    <div class="container">
      <h1 class="logo">
        <a class="logo_link" href="##">
          <img
            class="logo_link_img"
            src="https://evernote.com/img/logo/evernote/primary.svg"
            alt="evernote 品牌 logo"
          />
        </a>
      </h1>
      <hr class="line_bold" />
      <Guild></Guild>
      <LangueSocial></LangueSocial>
      <hr class="line_normal" />
      <CopyrightSecurity></CopyrightSecurity>
      <div class="logoIcon">
        <img src="https://evernote.com/img/footer/logo-icon.svg" alt="evernote 品牌 logo">
      </div>
    </div>
  </footer>
</template>
<script>
import Guild from '@/components/Guild';
import LangueSocial from '@/components/LangueSocial';
import CopyrightSecurity from '@/components/CopyrightSecurity';

export default {
  name: 'Footer',
  components: {
    Guild,
    LangueSocial,
    CopyrightSecurity,
  },
};
</script>
<style scoped>
.logo_link {
  display: inline-block;
  margin-bottom: 50px;
}
.line_bold {
  width: 100%;
  border-top: 3px solid black;
}
.line_normal {
  width: 100%;
  border-top: 1px solid gray;
}
.logoIcon {
  display: none;
}
@media (max-width: 1200px) {
  .bottom_row {
    padding: 0 20px;
  }
}
@media (max-width: 600px) {
  .logo_link {
    display: block;
    width: 45%;
  }
  .logo_link_img {
    width: 100%;
  }
  .logoIcon {
    display: block;
    text-align: center;
  }
}
</style>