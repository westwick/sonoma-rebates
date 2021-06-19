<template>
  <div>
    <div>
      <div class="hero-home">
        <div class="container mx-auto">
          <div class="grid grid-cols-2">
            <div class="cta">
              <h1>Rebates for home energy improvements</h1>
              <p>
                A brighter future starts at home. Earn rebates for
                energy-efficient solutions that help you save money and live
                comfortably.
              </p>
              <a href="#" class="button-cta">Get Started</a>
            </div>
          </div>
        </div>
      </div>
      <div class="home-info">
        <div class="container mx-auto">
          <div class="grid grid-cols-2">
            <div class="info-1">
              <h2>Live your best life</h2>
              <p>
                Sonoma Clean Power offers rebates and resources that make it
                easier to choose energy-saving products for your home. From
                appliances to heating and cooling systems, we’re here to help
                you live cleaner and greener. Apply today to receive customer or
                contractor rebates for qualified products and services.
              </p>
            </div>
            <div class="info-2">
              <h2>Applying is easy</h2>
              <ol class="apply-steps">
                <li>
                  <span>1</span> Browse the qualified project types for rebate
                  details.
                </li>
                <li>
                  <span>2</span>
                  Review the list of required documents and have them ready.
                </li>
                <li><span>3</span> Complete the online application form.</li>
              </ol>
            </div>
          </div>
        </div>
      </div>
      <div class="get-started">
        <div class="container mx-auto">
          <div class="flex flex-col content-center text-center">
            <p class="text-ugray">GET STARTED</p>
            <img src="~/assets/images/getstarted-icon.svg" />
            <h2>Please choose your project type below</h2>
          </div>
        </div>
      </div>
      <div class="rebate-types">
        <div class="container mx-auto rebate-types-container">
          <div class="all-rebates">All Rebates</div>
          <div class="grid grid-cols-3 gap-4">
            <div class="rebate-type">
              <h2>Heat Pump</h2>
              <p class="text-ugray">Save Up To $2,000</p>
              <NuxtLink to="/p/heatpump" class="button-cta"
                >View Details</NuxtLink
              >
            </div>
            <div class="rebate-type">
              <h2>Heat Pump Water Heater</h2>
              <p class="text-ugray">Save Up To $2,000</p>
              <a href="#" class="button-cta">View Details</a>
            </div>
            <div class="rebate-type">
              <h2>Induction Cooktop</h2>
              <p class="text-ugray">Save Up To $300</p>
              <a href="#" class="button-cta">View Details</a>
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
.hero-home {
  /* height: 680px; */
  background: url('~/assets/images/home.jpg') no-repeat center center;
  background-size: cover;
  display: flex;
  align-items: center;
  padding-top: 96px;
  padding-bottom: 160px;
}
.cta {
  background: rgba(56, 38, 88, 0.9);
  color: #fff;
  padding: 56px;
  margin-right: 40px;
}
.cta p {
  font-size: 20px;
  margin: 24px 0;
}
h1 {
  font-size: 40px;
  font-weight: bold;
  line-height: 1.2;
}
h2 {
  font-size: 36px;
  font-weight: bold;
  color: #382658;
}
.home-info {
  margin-top: -64px;
}
.info-1,
.info-2 {
  padding: 64px;
}
.info-1 {
  background: #fff;
  box-shadow: 0px -20px 40px #79aac429;
}
.info-1 h2 {
  color: #382658;
  margin-bottom: 16px;
}
.info-1 p {
  font-size: 18px;
}
.info-2 {
  background: #382658;
  color: #fff;
}
.info-2 h2 {
  color: #fff;
}
.apply-steps li {
  margin-top: 32px;
  font-size: 20px;
}
.apply-steps span {
  font-size: 1rem;
  width: 2rem;
  height: 2rem;

  border-radius: 50%;
  border: 1px solid #fff;
  color: #fff;
  font-weight: bold;
  margin-right: 16px;
  display: inline-flex;
  justify-content: center;
  align-items: center;
}
.get-started {
  padding: 96px 0 144px;
}
.get-started img {
  width: 96px;
  height: 96px;
  margin: 32px auto;
}
.all-rebates {
  width: 256px;
  height: 96px;
  border-bottom: 2px solid #382658;
  background: #fff;
  box-shadow: 0px 6px 20px #859daa29;
  display: flex;
  align-items: center;
  justify-content: center;
  color: #4f5263;
  text-transform: uppercase;
  font-weight: bold;
  font-size: 16px;
  margin: 0 auto;
  position: relative;
  top: -48px;
}
.rebate-types {
  margin-bottom: 208px;
}
.rebate-types-container {
  background: url('~/assets/images/background-lines.png') no-repeat center
    center;
  background-size: cover;
  padding: 0 16px;
}
.rebate-type {
  text-align: center;
  background: #fff;
  padding: 24px 0;
  margin: 128px 0;
  box-shadow: 0px 0px 20px #8599aa80;
}
.rebate-type h2 {
  font-size: 26px;
}
.rebate-type .text-ugray {
  margin: 12px 0 16px;
}
/* Sample `apply` at-rules with Tailwind CSS
.container {
@apply min-h-screen flex justify-center items-center text-center mx-auto;
}
*/
/* .container {
  margin: 0 auto;
  min-height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;
  text-align: center;
}

.title {
  font-family:
    'Quicksand',
    'Source Sans Pro',
    -apple-system,
    BlinkMacSystemFont,
    'Segoe UI',
    Roboto,
    'Helvetica Neue',
    Arial,
    sans-serif;
  display: block;
  font-weight: 300;
  font-size: 100px;
  color: #35495e;
  letter-spacing: 1px;
}

.subtitle {
  font-weight: 300;
  font-size: 42px;
  color: #526488;
  word-spacing: 5px;
  padding-bottom: 15px;
}

.links {
  padding-top: 15px;
} */
</style>
