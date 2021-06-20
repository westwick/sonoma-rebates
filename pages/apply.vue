<template>
  <div class="apply">
    <div class="apply-hero">
      <div class="apply-hero-container">
        <div class="container mx-auto">
          <div class="apply-hero-info">
            <p class="text-rebates">Part 1 of 3</p>
            <p class="text-apply">Apply for a Rebate</p>
          </div>
        </div>
      </div>
    </div>
    <div class="apply-main">
      <div class="apply-main-container">
        <div class="container mx-auto">
          <div class="grid grid-cols-4">
            <div class="col-span-3 bg-white mainform">
              <h1>Get started</h1>
              <p class="text-lg">
                Please ensure all the necessary fields are complete and accurate
                so that your application form can be successfully processed.
              </p>
              <p class="required-hint">
                <span class="text-red-500">*</span> Required fields
              </p>
              <div class="tabs-group">
                <span class="tab tab-active">Customer Details</span>
                <span class="tab">Rebate Details</span>
                <span class="tab">Sign &amp; Submit</span>
              </div>
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

<style>
@import url('~/assets/css/tabs.css');

.apply-hero-container {
  background: #382658;
  color: #fff;
  padding: 128px 0 184px;
}
.text-rebates {
  text-transform: uppercase;
  font-size: 16px;
  font-weight: bold;
}
.text-apply {
  font-size: 40px;
  font-weight: bold;
}
.apply-main h1 {
  color: #382658;
  font-size: 36px;
  font-weight: bold;
}
.apply-hero-info {
  padding-left: 56px;
}
.apply-main-container {
  margin-top: -64px;
}
.notice {
  padding: 40px;
}
.text-notice {
  color: #4f5263;
  font-weight: bold;
  margin-bottom: 8px;
}
.mainform {
  padding: 56px;
  padding-right: 104px;
}
.required-hint {
  color: #7e8da7;
  margin: 24px 0 48px 24px;
}
</style>
