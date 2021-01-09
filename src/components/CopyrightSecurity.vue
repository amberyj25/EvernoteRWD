<template>
  <div class="copyright_security">
    <div class="copyright">
      <p class="copyright_text">
        &copy 2020 Evernote Corporation。保留所有權利。
      </p>
    </div>
    <div class="security">
      <a class="security_link" href="##">安全性</a>
      <a class="security_link" href="##">法律資訊</a>
      <a class="security_link" href="##">隱私權</a>
    </div>
  </div>
</template>
<script>
export default {
  name: 'CopyrightSecurity',
};
</script>
<style>
.copyright_security {
  display: flex;
  justify-content: space-between;
  padding: 25px 0;
}
.copyright_text {
  color: gray;
}
.security_link {
  color: gray;
}
.security_link a:nth-child(2) {
  margin: 0 15px;
}
@media (max-width:1200px) {
  .security {
    line-height: 54px;
  }
}
@media (max-width: 600px) {
  .copyright_security {
    flex-direction: column;
  }
  .security {
    display: flex;
    justify-content: space-between;
    order: -1;
    padding: 50px 0;
  }
  .copyright_text {
    text-align: center;
    font-size: 0.5rem;
  }
}
</style>