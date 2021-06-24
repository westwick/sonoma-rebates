<template>
  <div id="footer">
    <div class="container mx-auto">
      <div class="footer">
        <div class="footer-logo">
          <img src="~/assets/images/logo.svg" />
        </div>
        <div class="footer-support">
          <p>Support@bayren.org</p>
          <p>1 (866) 878-6008</p>
        </div>
        <div class="footer-contact">
          <p>50 Santa Rosa Ave. 5th Floor</p>
          <p>Santa Rosa, CA 95404</p>
          <p class="footer-email">
            <a href="mailto:info@sonomacleanpower.org" class="link"
              >info@sonomacleanpower.org</a
            >
          </p>
        </div>
      </div>
    </div>
    <div class="footer-banner">
      <div
        class="
          container
          footer-banner-container
          mx-auto
          flex
          justify-between
          items-center
        "
      >
        <p>© 2021 Sonoma Clean Power Authority</p>
        <div class="footer-social">
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
#footer {
  border-top: 2px solid #f2f4f6;
}
.footer {
  padding: 96px 0 48px;
}
.footer-support {
  font-size: 25px;
  margin: 32px 0;
}
.footer-contact {
}
.footer-email {
  margin-top: 4px;
}
.footer-banner {
  background: #382658;
  color: #fff;
}
.footer-banner-container {
  height: 48px;
}
.footer-banner p {
  font-size: 20px;
}
.footer-social {
  font-size: 24px;
}
</style>
