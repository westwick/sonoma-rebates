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
          <div class="grid grid-cols-1 xl:grid-cols-4">
            <div
              class="
                xl:col-span-3
                bg-white
                mainform-container
                p-8
                md:p-12
                xl:pr-24
              "
            >
              <h1>Get started</h1>
              <p class="text-lg">
                Please ensure all the necessary fields are complete and accurate
                so that your application form can be successfully processed.
              </p>
              <p class="required-hint">
                <span class="text-red-500">*</span> Required fields
              </p>
              <div class="tabs-group flex-col md:flex-row mb-8">
                <div
                  class="tab"
                  :class="{ 'tab-active': step === 1 }"
                  @click="setStep(1)"
                >
                  Customer Details
                </div>
                <div
                  class="tab"
                  :class="{ 'tab-active': step === 2 }"
                  @click="setStep(2)"
                >
                  Rebate Details
                </div>
                <div
                  class="tab"
                  :class="{ 'tab-active': step === 3 }"
                  @click="setStep(3)"
                >
                  Sign &amp; Submit
                </div>
              </div>
              <div class="mainform">
                <form data-netlify="true" name="ajaxform" class="netlify-form">
                  <input type="hidden" name="account.pgeAccountNum" />
                  <input type="hidden" name="account.customerName" />
                  <input type="hidden" name="account.pgeGasSAID" />
                  <input type="hidden" name="account.pgeElectricSAID" />
                  <input type="hidden" name="account.customerPhone" />
                  <input type="hidden" name="account.customerEmail" />
                  <input type="hidden" name="account.language" />
                  <input type="hidden" name="account.householdGrossIncome" />
                  <input type="hidden" name="mailingAddress.street" />
                  <input type="hidden" name="mailingAddress.city" />
                  <input type="hidden" name="mailingAddress.state" />
                  <input type="hidden" name="mailingAddress.zip" />
                  <input
                    type="hidden"
                    name="mailingAddress.installingContractor"
                  />
                  <input type="hidden" name="mailingAddress.rebatePayee" />
                  <input type="hidden" name="mailingAddress.rebatePayeeName" />
                  <input
                    type="hidden"
                    name="mailingAddress.rebatePayeeStreet"
                  />
                  <input type="hidden" name="mailingAddress.rebatePayeeCity" />
                  <input type="hidden" name="mailingAddress.rebatePayeeState" />
                  <input type="hidden" name="mailingAddress.rebatePayeeZip" />
                  <input type="hidden" name="serviceAddress.street" />
                  <input type="hidden" name="serviceAddress.city" />
                  <input type="hidden" name="serviceAddress.state" />
                  <input type="hidden" name="serviceAddress.zip" />
                  <input type="hidden" name="property.yearBuilt" />
                  <input type="hidden" name="property.preProjectArea" />
                  <input type="hidden" name="property.postProjectArea" />
                  <input type="hidden" name="property.electricPanelUpgraded" />
                  <input type="hidden" name="property.otherElectricUpgrades" />
                  <input type="hidden" name="property.otherElectricUpgrades2" />
                  <input type="hidden" name="heatpump.dateInstalled" />
                  <input type="hidden" name="heatpump.existingFuelType" />
                  <input type="hidden" name="heatpump.ahriNumber" />
                  <input type="hidden" name="heatpump.newHpManufacturer" />
                  <input type="hidden" name="heatpump.newHpModel" />
                  <input type="hidden" name="heatpump.serial" />
                  <input type="hidden" name="heatpump.hpUnitsInstalled" />
                  <input type="hidden" name="heatpump.hspfRating" />
                  <input type="hidden" name="heatpump.seerRating" />
                  <input type="hidden" name="heatpump.measureCostToCustomer" />
                  <input type="hidden" name="heatpump.existingHeatType" />
                  <input type="hidden" name="heatpump.existingHeatSize" />
                  <input type="hidden" name="heatpump.existingCoolingType" />
                  <input type="hidden" name="heatpump.existingCoolingSize" />
                  <input type="hidden" name="heatpump.newPumpType" />
                  <input type="hidden" name="heatpump.newPumpSize" />
                  <input type="hidden" name="heatpump.proofOfPermitClosure" />
                  <input type="hidden" name="heatpump.casSheet" />
                  <input type="hidden" name="heatpump.photoOld" />
                  <input type="hidden" name="heatpump.photoNew" />
                  <input
                    type="hidden"
                    name="heatpumpwaterheater.dateInstalled"
                  />
                  <input
                    type="hidden"
                    name="heatpumpwaterheater.existingWaterHeaterFuelType"
                  />
                  <input type="hidden" name="heatpumpwaterheater.newHpwhMake" />
                  <input
                    type="hidden"
                    name="heatpumpwaterheater.newHpwhModel"
                  />
                  <input
                    type="hidden"
                    name="heatpumpwaterheater.newHpwhTankSize"
                  />
                  <input
                    type="hidden"
                    name="heatpumpwaterheater.newHpwhEfficiencyFactory"
                  />
                  <input type="hidden" name="heatpumpwaterheater.wifiEnabled" />
                  <input type="hidden" name="heatpumpwaterheater.macIdOrSn" />
                  <input
                    type="hidden"
                    name="heatpumpwaterheater.thermostaticMixingValve"
                  />
                  <input
                    type="hidden"
                    name="heatpumpwaterheater.measureCostToCustomer"
                  />
                  <input
                    type="hidden"
                    name="heatpumpwaterheater.proofOfMixingValue"
                  />
                  <input type="hidden" name="heatpumpwaterheater.casSheet" />
                  <input type="hidden" name="heatpumpwaterheater.photoOld" />
                  <input type="hidden" name="heatpumpwaterheater.photoNew" />
                  <input type="hidden" name="inductioncooktop.dateInstalled" />
                  <input
                    type="hidden"
                    name="inductioncooktop.existingFuelType"
                  />
                  <input
                    type="hidden"
                    name="inductioncooktop.existingApplianceType"
                  />
                  <input
                    type="hidden"
                    name="inductioncooktop.newApplianceType"
                  />
                  <input type="hidden" name="inductioncooktop.connectedLoad" />
                  <input type="hidden" name="inductioncooktop.manufacturer" />
                  <input type="hidden" name="inductioncooktop.model" />
                  <input type="hidden" name="documents.electricalPanel" />
                  <input type="hidden" name="documents.electricalPanelNew" />
                  <input
                    type="hidden"
                    name="documents.electricalPanelInvoice"
                  />
                  <input
                    type="hidden"
                    name="documents.electrificationInvoice"
                  />
                  <input type="hidden" name="documents.cappedGasLines" />
                  <input type="hidden" name="documents.itemizedInvoice" />
                  <input type="hidden" name="documents.applicationForm" />
                  <input type="hidden" name="documents.w9" />
                  <input type="hidden" name="documents.pgeBill" />
                  <input type="hidden" name="signature" />
                </form>
                <form
                  method="POST"
                  action="/submit"
                  name="vueform"
                  id="mainform"
                >
                  <div v-if="step === 1">
                    <FormsCustomerDetails
                      :account="account"
                      :validator="$v"
                      class="mb-8"
                    />
                    <FormsServiceAddress
                      :serviceAddress="serviceAddress"
                      :validator="$v"
                      class="mb-8"
                    />
                    <FormsMailingAddress
                      :mailingAddress="mailingAddress"
                      :validator="$v"
                      @sameAs="handleSameAs"
                      @sameAs2="handleSameAs2"
                      class="mb-8"
                    />
                    <FormsProperty :property="property" :validator="$v" />
                    <button
                      class="button-cta mx-auto mt-8 mb-8"
                      @click.prevent="setStep(2)"
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
                      <div class="grid grid-cols-1 md:grid-cols-1 gap-x-4">
                        <div>
                          <div class="form-group">
                            <label class="form__label text-base"
                              >Photo of existing electrical panel</label
                            >
                            <FormsUploadButton
                              v-model="$v.documents.electricalPanel.$model"
                              :uploadPath="account.pgeAccountNum"
                            />
                          </div>
                        </div>
                        <div>
                          <div class="form-group">
                            <label class="form__label text-base"
                              >Photo of new electrical panel (if upgraded)
                            </label>

                            <FormsUploadButton
                              v-model="$v.documents.electricalPanelNew.$model"
                              :uploadPath="account.pgeAccountNum"
                            />
                          </div>
                        </div>
                      </div>
                      <div class="grid grid-cols-1 md:grid-cols-1 gap-x-4">
                        <div>
                          <div class="form-group">
                            <label class="form__label text-base"
                              >Itemized invoice for electrical panel upgrade (if
                              applicable)</label
                            >
                            <FormsUploadButton
                              v-model="
                                $v.documents.electricalPanelInvoice.$model
                              "
                              :uploadPath="account.pgeAccountNum"
                            />
                          </div>
                        </div>
                        <div>
                          <div class="form-group">
                            <label class="form__label text-base"
                              >Itemized invoice for other electrification
                              measures installed at the site (if applicable)
                            </label>

                            <FormsUploadButton
                              v-model="
                                $v.documents.electrificationInvoice.$model
                              "
                              :uploadPath="account.pgeAccountNum"
                            />
                          </div>
                        </div>
                      </div>
                      <div class="grid grid-cols-1 md:grid-cols-1 gap-x-4">
                        <div>
                          <div class="form-group">
                            <label class="form__label text-base"
                              >Photo of capped gas line(s) for electrification
                              projects (if applicable)</label
                            >
                            <FormsUploadButton
                              v-model="$v.documents.cappedGasLines.$model"
                              :uploadPath="account.pgeAccountNum"
                            />
                          </div>
                        </div>
                        <div>
                          <div class="form-group">
                            <label class="form__label text-base"
                              >Itemized invoice/receipt paid by customer with
                              model number(s)
                            </label>

                            <FormsUploadButton
                              v-model="$v.documents.itemizedInvoice.$model"
                              :uploadPath="account.pgeAccountNum"
                            />
                          </div>
                        </div>
                      </div>
                      <div class="grid grid-cols-1 md:grid-cols-1 gap-x-4">
                        <div>
                          <div class="form-group">
                            <label class="form__label text-base"
                              >Application Form</label
                            >
                            <FormsUploadButton
                              v-model="$v.documents.applicationForm.$model"
                              :uploadPath="account.pgeAccountNum"
                            />
                          </div>
                        </div>
                        <div>
                          <div class="form-group">
                            <label class="form__label"
                              >W-9 signed by recipient of payment (if other than
                              Account Holder)
                            </label>

                            <FormsUploadButton
                              v-model="$v.documents.w9.$model"
                              :uploadPath="account.pgeAccountNum"
                            />
                          </div>
                        </div>
                      </div>
                      <div class="grid grid-cols-1 md:grid-cols-1 gap-x-4">
                        <div>
                          <div class="form-group">
                            <label class="form__label"
                              >Copy of customer PG&amp;E bill showing SCP
                              membership</label
                            >
                            <FormsUploadButton
                              v-model="$v.documents.pgeBill.$model"
                              :uploadPath="account.pgeAccountNum"
                            />
                          </div>
                        </div>
                        <div>
                          <!-- placeholder for next form elem! -->
                        </div>
                      </div>
                    </div>
                    <button
                      class="button-cta mx-auto mt-8 mb-8"
                      @click.prevent="setStep(3)"
                    >
                      Continue
                    </button>
                    <!-- <div class="bg-gray-100 p-8 mt-8">
                      <p class="form-section-name mb-4">Supporting Documents</p>
                      <p class="font-lg mb-4">Please upload the following:</p>
                    </div> -->
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
                        Please type your name to provide your signature
                        below.<span class="r">*</span>
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
import Robodog from '@uppy/robodog'

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
        rebatePayeeName: '',
        rebatePayeeStreet: '',
        rebatePayeeCity: '',
        rebatePayeeState: '',
        rebatePayeeZip: '',
      },
      serviceAddress: {
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
        otherElectricUpgrades2: '',
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
        proofOfPermitClosure: '',
        casSheet: '',
        photoOld: '',
        photoNew: '',
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
        proofOfMixingValue: '',
        casSheet: '',
        photoOld: '',
        photoNew: '',
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
      documents: {
        electricalPanel: '',
        electricalPanelNew: '',
        electricalPanelInvoice: '',
        electrificationInvoice: '',
        cappedGasLines: '',
        itemizedInvoice: '',
        applicationForm: '',
        w9: '',
        pgeBill: '',
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
        rebatePayeeName: { required },
        rebatePayeeStreet: { required },
        rebatePayeeCity: { required },
        rebatePayeeState: { required },
        rebatePayeeZip: { required },
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
        otherElectricUpgrades2: {},
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
        proofOfPermitClosure: this.heatpumpSelected ? { required } : {},
        casSheet: {},
        photoOld: {},
        photoNew: {},
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
        macIdOrSn: this.heatpumpwaterheaterSelected ? {} : {},
        thermostaticMixingValve: this.heatpumpwaterheaterSelected
          ? { required }
          : {},
        measureCostToCustomer: this.heatpumpwaterheaterSelected
          ? { required }
          : {},
        proofOfMixingValue: this.heatpumpwaterheaterSelected
          ? { required }
          : {},
        casSheet: {},
        photoOld: {},
        photoNew: {},
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
      documents: {
        electricalPanel: {},
        electricalPanelNew: {},
        electricalPanelInvoice: {},
        electrificationInvoice: {},
        cappedGasLines: {},
        itemizedInvoice: {},
        applicationForm: {},
        w9: {},
        pgeBill: {},
      },
      signature: { required },
    }
  },
  methods: {
    handleSameAs(e) {
      if (e) {
        this.mailingAddress.street = this.serviceAddress.street
        this.mailingAddress.city = this.serviceAddress.city
        this.mailingAddress.state = this.serviceAddress.state
        this.mailingAddress.zip = this.serviceAddress.zip
      } else {
        this.mailingAddress.street = ''
        this.mailingAddress.city = ''
        this.mailingAddress.state = ''
        this.mailingAddress.zip = ''
      }
    },
    handleSameAs2(e) {
      if (e) {
        this.mailingAddress.rebatePayeeStreet = this.serviceAddress.street
        this.mailingAddress.rebatePayeeCity = this.serviceAddress.city
        this.mailingAddress.rebatePayeeState = this.serviceAddress.state
        this.mailingAddress.rebatePayeeZip = this.serviceAddress.zip
      } else {
        this.mailingAddress.rebatePayeeStreet = ''
        this.mailingAddress.rebatePayeeCity = ''
        this.mailingAddress.rebatePayeeState = ''
        this.mailingAddress.rebatePayeeZip = ''
      }
    },
    setStep(newStep) {
      if (newStep === 2) {
        this.$v.account.$touch()
        this.$v.mailingAddress.$touch()
        this.$v.serviceAddress.$touch()
        this.$v.property.$touch()

        if (
          this.$v.account.$invalid ||
          this.$v.mailingAddress.$invalid ||
          this.$v.serviceAddress.$invalid ||
          this.$v.property.$invalid
        ) {
          alert(
            'Some information is missing. Please review your form and ensure all required fields are complete.'
          )
          return
        }
      }

      if (newStep === 3) {
        this.$v.account.$touch()
        this.$v.mailingAddress.$touch()
        this.$v.serviceAddress.$touch()
        this.$v.property.$touch()
        this.$v.heatpump.$touch()
        this.$v.heatpumpwaterheater.$touch()
        this.$v.inductioncooktop.$touch()

        if (
          this.$v.account.$invalid ||
          this.$v.mailingAddress.$invalid ||
          this.$v.serviceAddress.$invalid ||
          this.$v.property.$invalid ||
          this.$v.heatpump.$invalid ||
          this.$v.heatpumpwaterheater.$invalid ||
          this.$v.inductioncooktop.$invalid
        ) {
          alert(
            'Some information is missing. Please review your form and ensure all required fields are complete.'
          )
          return
        }
      }

      this.step = newStep
      const tabs = document.querySelector('.tabs-group')
      const viewport = tabs.getBoundingClientRect()
      const top = viewport.top + document.documentElement.scrollTop
      window.scrollTo(0, top)
    },
    handleUpload() {
      console.log('robodog', Robodog)
      const resultPromise = Robodog.pick({
        target: 'body',
        params: {
          auth: { key: '5314f85b82984dce8d0194ac88be17e3' },
          template_id: '4a6598acae9342228925ffbbc7f6b243',
          fields: {
            path: 'test',
          },
        },
      })
      console.log('promise', resultPromise)
      resultPromise.then((bundle) => {
        console.log('bundle', bundle)
      })
    },
    handleSubmit() {
      this.$v.$touch()
      if (this.$v.$invalid) {
        alert(
          'Some information is missing. Please review your form and ensure all required fields are complete.'
        )
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
          .then(() => {
            console.log('Form successfully submitted')
            this.$router.push('/thank-you')
          })
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
input[type='number'],
select {
  width: 100%;
  font-size: 18px;
  margin-bottom: 24px;
  border: 1px solid #a9bada;
  padding: 0.75rem 1rem;
}
input[type='text']:focus,
input[type='number']:focus,
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
  font-size: 14px;
  margin-bottom: 3px;
}
.form-group--error .form__label {
  color: rgb(239, 68, 68);
}
.form-group--error input,
.form-group--error select {
  border-color: rgb(239, 68, 68);
  margin-bottom: 0;
}
.form-group--error .file-upload-button {
  margin-bottom: 0;
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
  border: 1px solid #bac8e0;
  padding: 16px;
}
.product-type.product-selected {
  background: #fff;
  border-color: #93c4fe;
}

input[type='checkbox'] {
  border-radius: 3px;
}
.netlify-form {
  display: none;
}
label.disabled {
  color: #aaa;
}
input.disabled {
  border: 1px solid #ccc !important;
}
.has-tooltip:hover .tooltip,
.has-tooltip.hover .tooltip {
  visibility: visible;
  z-index: 50;
}
.tooltip {
  position: absolute;
  visibility: hidden;
}
</style>
