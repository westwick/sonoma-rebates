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
                    <div class="bg-gray-100 p-8">
                      <p class="form-section-name mb-4">Products</p>
                      <p class="font-lg mb-4">
                        Select the product(s) you are submitting as part of your
                        application.
                      </p>
                      <div class="rebate-selections">
                        <div
                          class="product-type mb-2"
                          :class="{ 'product-selected': heatpumpSelected }"
                        >
                          <div class="checkbox-wrap">
                            <input
                              type="checkbox"
                              name="heatpump"
                              id="heatpump"
                              v-model="heatpumpSelected"
                            />
                            <label for="heatpump">Heat pump</label>
                          </div>
                          <div
                            v-if="heatpumpSelected"
                            class="product-wrap mt-8"
                          >
                            <FormsProductHeatpump
                              :heatpump="heatpump"
                              :validator="$v"
                            />
                          </div>
                        </div>
                        <div
                          class="product-type mb-2"
                          :class="{
                            'product-selected': heatpumpwaterheaterSelected,
                          }"
                        >
                          <div class="checkbox-wrap">
                            <input
                              type="checkbox"
                              name="heatpumpwaterheater"
                              id="heatpumpwaterheater"
                              v-model="heatpumpwaterheaterSelected"
                            />
                            <label for="heatpumpwaterheater"
                              >Heat pump water heater</label
                            >
                          </div>
                          <div
                            v-if="heatpumpwaterheaterSelected"
                            class="product-wrap mt-8"
                          >
                            <FormsProductHeatpumpwaterheater
                              :heatpumpwaterheater="heatpumpwaterheater"
                              :validator="$v"
                            />
                          </div>
                        </div>
                        <div
                          class="product-type"
                          :class="{
                            'product-selected': inductioncooktopSelected,
                          }"
                        >
                          <div class="checkbox-wrap">
                            <input
                              type="checkbox"
                              name="inductioncooktop"
                              id="inductioncooktop"
                              v-model="inductioncooktopSelected"
                            />
                            <label for="inductioncooktop"
                              >Induction cooktop</label
                            >
                          </div>
                          <div
                            v-if="inductioncooktopSelected"
                            class="product-wrap mt-8"
                          >
                            <FormsProductInductionCooktop
                              :inductioncooktop="inductioncooktop"
                              :validator="$v"
                            />
                          </div>
                        </div>
                      </div>
                    </div>
                    <div class="bg-gray-100 p-8 mt-8">
                      <p class="form-section-name mb-4">Supporting Documents</p>
                      <p class="font-lg mb-4">Please upload the following:</p>
                    </div>
                  </div>
                  <div v-if="step === 3">
                    <div class="bg-gray-100 p-8">
                      <p class="form-section-name mb-8">Signature</p>
                      <p class="font-xl mb-4">
                        This Residential Rebate Application cannot be processed
                        unless all of the appropriate fields on this application
                        are complete. Please be sure you have read the Terms and
                        Conditions of this application.
                      </p>
                      <p class="font-xl mb-4">
                        I have read and understand the terms and conditions. I
                        certify that the information I have provided is true and
                        correct and the product(s) and/or equipment for which I
                        am requesting a rebate meets the requirements in this
                        application.
                      </p>
                      <p class="font-xl mb-4">
                        Please type your name to provide your signature below.
                      </p>
                      <div
                        class="form-group"
                        :class="{
                          'form-group--error': $v.signature.$error,
                        }"
                      >
                        <input
                          class="form__input"
                          type="text"
                          name="mailingAddress.street"
                          v-model="$v.signature.$model"
                        />
                      </div>
                      <div
                        class="error"
                        v-if="$v.signature.$error && !$v.signature.required"
                      >
                        * Required
                      </div>
                      <div class="signature">{{ signature }}</div>
                    </div>
                    <button
                      class="button-cta mt-8"
                      @click.prevent="handleSubmit()"
                    >
                      Submit
                    </button>
                  </div>
                </form>
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
      heatpumpSelected: false,
      heatpumpwaterheaterSelected: false,
      inductioncooktopSelected: false,
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
      heatpump: {
        dateInstalled: '',
        existingFuelType: '',
        ahriNumber: '',
        newHpManufacturer: '',
        newHpModel: '',
        serial: '',
        hpUnitsInstalled: '',
        hspfRating: '',
        seerRating: '',
        measureCostToCustomer: '',
        existingHeatType: '',
        existingHeatSize: '',
        existingCoolingType: '',
        existingCoolingSize: '',
        newPumpType: '',
        newPumpSize: '',
      },
      heatpumpwaterheater: {
        dateInstalled: '',
        existingWaterHeaterFuelType: '',
        newHpwhMake: '',
        newHpwhModel: '',
        newHpwhTankSize: '',
        newHpwhEfficiencyFactory: '',
        wifiEnabled: '',
        macIdOrSn: '',
        thermostaticMixingValve: '',
        measureCostToCustomer: '',
      },
      inductioncooktop: {
        dateInstalled: '',
        existingFuelType: '',
        existingApplianceType: '',
        newApplianceType: '',
        connectedLoad: '',
        manufacturer: '',
        model: '',
      },
      signature: '',
    }
  },
  validations() {
    return {
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
      heatpump: {
        dateInstalled: this.heatpumpSelected ? { required } : {},
        existingFuelType: this.heatpumpSelected ? { required } : {},
        ahriNumber: this.heatpumpSelected ? { required } : {},
        newHpManufacturer: this.heatpumpSelected ? { required } : {},
        newHpModel: this.heatpumpSelected ? { required } : {},
        serial: this.heatpumpSelected ? { required } : {},
        hpUnitsInstalled: this.heatpumpSelected ? { required } : {},
        hspfRating: this.heatpumpSelected ? { required } : {},
        seerRating: this.heatpumpSelected ? { required } : {},
        measureCostToCustomer: this.heatpumpSelected ? { required } : {},
        existingHeatType: this.heatpumpSelected ? { required } : {},
        existingHeatSize: this.heatpumpSelected ? { required } : {},
        existingCoolingType: this.heatpumpSelected ? { required } : {},
        existingCoolingSize: this.heatpumpSelected ? { required } : {},
        newPumpType: this.heatpumpSelected ? { required } : {},
        newPumpSize: this.heatpumpSelected ? { required } : {},
      },
      heatpumpwaterheater: {
        dateInstalled: this.heatpumpwaterheaterSelected ? { required } : {},
        existingWaterHeaterFuelType: this.heatpumpwaterheaterSelected
          ? { required }
          : {},
        newHpwhMake: this.heatpumpwaterheaterSelected ? { required } : {},
        newHpwhModel: this.heatpumpwaterheaterSelected ? { required } : {},
        newHpwhTankSize: this.heatpumpwaterheaterSelected ? { required } : {},
        newHpwhEfficiencyFactory: this.heatpumpwaterheaterSelected
          ? { required }
          : {},
        wifiEnabled: this.heatpumpwaterheaterSelected ? { required } : {},
        macIdOrSn: this.heatpumpwaterheaterSelected ? { required } : {},
        thermostaticMixingValve: this.heatpumpwaterheaterSelected
          ? { required }
          : {},
        measureCostToCustomer: this.heatpumpwaterheaterSelected
          ? { required }
          : {},
      },
      inductioncooktop: {
        dateInstalled: this.inductioncooktopSelected ? { required } : {},
        existingFuelType: this.inductioncooktopSelected ? { required } : {},
        existingApplianceType: this.inductioncooktopSelected
          ? { required }
          : {},
        newApplianceType: this.inductioncooktopSelected ? { required } : {},
        connectedLoad: this.inductioncooktopSelected ? { required } : {},
        manufacturer: this.inductioncooktopSelected ? { required } : {},
        model: this.inductioncooktopSelected ? { required } : {},
      },
      signature: { required },
    }
  },
  methods: {
    setStep(newStep) {
      this.step = newStep
      const tabs = document.querySelector('.tabs-group')
      const viewport = tabs.getBoundingClientRect()
      const top = viewport.top + document.documentElement.scrollTop
      window.scrollTo(0, top)
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
        if (this.heatpumpSelected) {
          for (var key in this.heatpump) {
            formData.append(`heatpump.${key}`, this.heatpump[key])
          }
        }
        if (this.heatpumpwaterheaterSelected) {
          for (var key in this.heatpumpwaterheater) {
            formData.append(
              `heatpumpwaterheater.${key}`,
              this.heatpumpwaterheater[key]
            )
          }
        }
        if (this.inductioncooktopSelected) {
          for (var key in this.inductioncooktop) {
            formData.append(
              `inductioncooktop.${key}`,
              this.inductioncooktop[key]
            )
          }
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
.signature {
  font-family: cursive;
  font-size: 24px;
}
.checkbox-wrap {
  width: 100%;
  display: flex;
  align-items: center;
}
.checkbox-wrap label {
  margin: 0 0 0 16px;
  cursor: pointer;
}
.product-type {
  border: 1px solid rgba(99, 131, 188, 1);
  padding: 16px;
}
.product-type.product-selected {
  background: #fff;
  border-color: rgba(0, 117, 253, 1);
}

input[type='checkbox'] {
  border-radius: 3px;
}
</style>
