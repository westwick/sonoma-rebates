<template>
  <div id="banner">
    <div class="container mx-auto">
      <div class="link-back ml-4 md:ml-0">
        <a href="#" class="text-sm md:text-base">‹ Visit Sonoma Clean Power</a>
      </div>
      <div class="banner-right hidden md:flex md:items-center">
        <div class="banner-contact">
          <a href="tel:18668786008">1 (866) 878-6008</a> |
          <a href="mailto:support@bayren.org">Contact Us</a>
        </div>
        <div class="banner-social">
          <a href="https://www.facebook.com/SonomaCleanPower/" target="_blank"
            ><i class="fab fa-facebook-square"></i
          ></a>
          <a href="https://twitter.com/SonomaCleanPow" target="_blank"
            ><i class="fab fa-twitter-square"></i
          ></a>
          <a href="https://www.instagram.com/sonomacleanpower/" target="_blank"
            ><i class="fab fa-instagram-square"></i
          ></a>
          <a
            href="https://www.youtube.com/channel/UCtyV9LHYkxqGn-eysEIxkaw"
            target="_blank"
            ><i class="fab fa-youtube-square"></i
          ></a>
          <a
            href="https://www.linkedin.com/company/sonoma-clean-power/"
            target="_blank"
            ><i class="fab fa-linkedin"></i
          ></a>
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
  /* display: flex; */
  /* align-items: center; */
}
.banner-contact {
  padding-right: 96px;
}
.banner-social {
  font-size: 24px;
}
</style>
