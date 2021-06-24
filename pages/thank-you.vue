<template>
  <div class="product-page">
    <div class="product-hero">
      <div class="grid grid-cols-2">
        <div class="product-hero-info-container">
          <div class="product-hero-info">
            <p class="text-rebates">Rebates</p>
            <p class="text-product-title">Thank you for applying</p>
          </div>
        </div>
        <div class="product-hero-img"></div>
      </div>
    </div>
    <div class="product-main">
      <div class="product-main-container">
        <div class="container mx-auto">
          <div class="grid grid-cols-4">
            <div class="product-info thanks col-span-3 bg-white p-14 pr-20">
              <h2>Your application has been submitted</h2>
              <p class="text-lg mb-8">
                You will receive an email confirming the submission of your
                rebate application.
              </p>
              <NuxtLink to="/" class="button-cta">Return Home</NuxtLink>
            </div>
            <div class="bg-gray-100 notice">
              <p class="text-notice">NOTICE</p>
              <p class="font-bold">
                All requests will be handled within seven business days.
              </p>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {}
</script>

<style>
@import url('~/assets/css/tabs.css');
.thanks {
  min-height: 50vh;
}
.tabs-group {
  margin-bottom: 48px;
}

.product-hero-info-container {
  background: #382658;
  color: #fff;
  padding: 128px 0 184px;
}
.product-hero-info {
  width: 536px;
  margin: 0 auto;
  padding-left: 48px;
}
.product-hero-img {
  background: url('~/assets/images/product-hero.jpg') no-repeat top center;
}
.text-rebates {
  text-transform: uppercase;
  font-size: 16px;
  font-weight: 600;
}
.text-product-title {
  font-size: 40px;
  font-weight: bold;
}

.product-main-container {
  margin-top: -64px;
}
.product-headline {
  font-size: 40px;
  color: #382658;
  margin-top: 56px;
  margin-bottom: 32px;
  font-weight: bold;
}
.product-apply-now {
  padding: 40px;
}
.how-to-apply {
  color: #4f5263;
  font-weight: bold;
  margin-top: 16px;
}

.product-tabs-container {
  border-top: 2px solid #f2f4f6;
  padding-top: 48px;
  padding-bottom: 48px;
}
.product-qualifications-text h1 {
  font-size: 36px;
  font-weight: bold;
  color: #382658;
}
.product-qualifications-text h2 {
  font-size: 26px;
  font-weight: bold;
  color: #4f5263;
  margin-top: 8px;
  margin-bottom: 24px;
}
.product-qualifications-text p {
  font-size: 20px;
  margin-bottom: 16px;
}
.product-qualifications-text p img {
  display: inline;
  margin-right: 48px;
}
</style>
