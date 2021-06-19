<template>
  <div id="banner">
    <div class="container mx-auto">
      <div class="link-back">
        <a href="#">‹ Visit Sonoma Clean Power</a>
      </div>
      <div class="banner-right">
        <div class="banner-contact">1 (866) 878-6008 | Contact Us</div>
        <div class="banner-social">
          <i class="fab fa-facebook-square"></i>
          <i class="fab fa-twitter-square"></i>
          <i class="fab fa-instagram-square"></i>
          <i class="fab fa-youtube-square"></i>
          <i class="fab fa-linkedin"></i>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {}
</script>

<style>
#banner {
  width: 100%;
  height: 48px;
  background: #382658;
  color: #fff;
  display: flex;
  align-items: center;
}
#banner .container {
  display: flex;
  align-items: center;
  justify-content: space-between;
}
.banner-right {
  display: flex;
  align-items: center;
}
.banner-contact {
  padding-right: 96px;
}
.banner-social {
  font-size: 24px;
}
</style>
