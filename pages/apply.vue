<template>
  <div class="apply">
    <div class="apply-hero">
      <div class="apply-hero-container">
        <div class="container mx-auto">
          <div class="apply-hero-info">
            <p class="text-rebates">Part {{ step }} of 3</p>
            <p class="text-apply">Apply for a Rebate</p>
          </div>
        </div>
      </div>
    </div>
    <div class="apply-main">
      <div class="apply-main-container">
        <div class="container mx-auto">
          <div class="grid grid-cols-4">
            <div class="col-span-3 bg-white mainform-container">
              <h1>Get started</h1>
              <p class="text-lg">
                Please ensure all the necessary fields are complete and accurate
                so that your application form can be successfully processed.
              </p>
              <p class="required-hint">
                <span class="text-red-500">*</span> Required fields
              </p>
              <div class="tabs-group mb-8">
                <span
                  class="tab"
                  :class="{ 'tab-active': step === 1 }"
                  @click="setStep(1)"
                  >Customer Details</span
                >
                <span
                  class="tab"
                  :class="{ 'tab-active': step === 2 }"
                  @click="setStep(2)"
                  >Rebate Details</span
                >
                <span
                  class="tab"
                  :class="{ 'tab-active': step === 3 }"
                  @click="setStep(3)"
                  >Sign &amp; Submit</span
                >
              </div>
              <div class="mainform">
                <form
                  method="POST"
                  action="/submit"
                  name="ajaxform"
                  id="mainform"
                  data-netlify="true"
                >
                  <div v-if="step === 1">
                    <FormsCustomerDetails
                      :account="account"
                      :validator="$v"
                      class="mb-8"
                    />
                    <FormsMailingAddress
                      :mailingAddress="mailingAddress"
                      :validator="$v"
                      class="mb-8"
                    />
                    <FormsServiceAddress
                      :serviceAddress="serviceAddress"
                      :validator="$v"
                      class="mb-8"
                    />
                    <FormsProperty :property="property" :validator="$v" />
                    <button
                      class="button-cta mx-auto mt-8 mb-8"
                      @click="setStep(2)"
                    >
                      Continue
                    </button>
                  </div>
                  <div v-if="step === 2">
                    <h1>Products TBD</h1>
                  </div>
                  <div v-if="step === 3">
                    <h1>Sign</h1>
                  </div>
                </form>

                <p>dev</p>
                <button @click="handleSubmit()">Submit AJAX</button>
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

<script>
import { required } from 'vuelidate/lib/validators'

export default {
  data() {
    return {
      step: 1,
      account: {
        pgeAccountNum: '',
        customerName: '',
        pgeGasSAID: '',
        pgeElectricSAID: '',
        customerPhone: '',
        customerEmail: '',
        language: '',
        householdGrossIncome: '',
      },
      mailingAddress: {
        street: '',
        city: '',
        state: '',
        zip: '',
        installingContractor: '',
        rebatePayee: '',
        whereToSend: '',
      },
      serviceAddress: {
        sameAsMailing: false,
        street: '',
        city: '',
        state: '',
        zip: '',
      },
      property: {
        yearBuilt: '',
        preProjectArea: '',
        postProjectArea: '',
        electricPanelUpgraded: '',
        otherElectricUpgrades: '',
      },
    }
  },
  validations: {
    account: {
      pgeAccountNum: { required },
      customerName: { required },
      pgeGasSAID: { required },
      pgeElectricSAID: { required },
      customerPhone: { required },
      customerEmail: { required },
      language: { required },
    },
    mailingAddress: {
      street: { required },
      city: { required },
      state: { required },
      zip: { required },
      installingContractor: { required },
      rebatePayee: { required },
      whereToSend: { required },
    },
    serviceAddress: {
      street: { required },
      city: { required },
      state: { required },
      zip: { required },
    },
    property: {
      yearBuilt: { required },
      preProjectArea: { required },
      postProjectArea: { required },
      electricPanelUpgraded: { required },
      otherElectricUpgrades: { required },
    },
  },
  methods: {
    setStep(newStep) {
      this.step = newStep
    },
    handleSubmit() {
      this.$v.$touch()
      if (this.$v.$invalid) {
        alert('form incomplete')
      } else {
        let formData = new FormData()
        formData.append('form-name', 'ajaxform')
        for (var key in this.account) {
          formData.append(`account.${key}`, this.account[key])
        }
        for (var key in this.mailingAddress) {
          formData.append(`mailingAddress.${key}`, this.mailingAddress[key])
        }
        for (var key in this.serviceAddress) {
          formData.append(`serviceAddress.${key}`, this.serviceAddress[key])
        }
        for (var key in this.property) {
          formData.append(`property.${key}`, this.property[key])
        }
        let postbody = new URLSearchParams(formData).toString()
        fetch('/', {
          method: 'POST',
          headers: { 'Content-Type': 'application/x-www-form-urlencoded' },
          body: postbody,
        })
          .then(() => console.log('Form successfully submitted'))
          .catch((error) => alert(error))
      }
    },
  },
}
</script>

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
  max-height: 100vh;
}
.text-notice {
  color: #4f5263;
  font-weight: bold;
  margin-bottom: 8px;
}
.mainform-container {
  padding: 56px;
  padding-right: 104px;
}
.required-hint {
  color: #7e8da7;
  margin: 24px 0 48px 24px;
}
.form-section-name {
  color: rgba(79, 82, 99, 1);
  font-weight: bold;
  font-size: 20px;
}

label {
  display: block;
  font-size: 18px;
  margin-bottom: 8px;
}
input[type='text'],
select {
  width: 100%;
  font-size: 18px;
  margin-bottom: 24px;
  border: 1px solid #a9bada;
  padding: 0.75rem 1rem;
}
input[type='text']:focus,
select:focus {
  border-color: rgba(79, 82, 99, 1);
}
select:not(:valid) {
  color: #9a9a9a;
}
option {
  color: black;
}
span.r,
.error {
  color: rgb(239, 68, 68);
}
.error {
  position: absolute;
  margin-top: -24px;
  font-size: 14px;
}
.form-group--error .form__label {
  color: rgb(239, 68, 68);
}
.form-group--error input,
.form-group--eror select {
  border-color: rgb(239, 68, 68);
}
.label-hint {
  font-size: 15px;
  color: #777;
}
</style>
