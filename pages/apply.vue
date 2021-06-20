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
                <span class="tab tab-active">Customer Details</span>
                <span class="tab">Rebate Details</span>
                <span class="tab">Sign &amp; Submit</span>
              </div>
              <div class="mainform">
                <form
                  method="POST"
                  action="/submit"
                  name="test"
                  id="mainform"
                  data-netlify="true"
                >
                  <input
                    type="hidden"
                    name="form-name"
                    value="name_of_my_form"
                  />
                  <div class="customer-details">
                    <div class="bg-gray-100 p-8">
                      <p class="form-section-name">Account Information</p>
                      <div class="grid grid-cols-2 gap-x-8">
                        <div>
                          <div
                            class="form-group"
                            :class="{
                              'form-group--error':
                                $v.account.pgeAccountNum.$error,
                            }"
                          >
                            <label class="form__label"
                              >PG&amp;E Account #<span class="r">*</span></label
                            >
                            <input
                              class="form__input"
                              type="text"
                              name="pgeAccountNum"
                              v-model="$v.account.pgeAccountNum.$model"
                            />
                          </div>
                          <div
                            class="error"
                            v-if="
                              $v.account.pgeAccountNum.$error &&
                              !$v.account.pgeAccountNum.required
                            "
                          >
                            * Required
                          </div>

                          <div
                            class="form-group"
                            :class="{
                              'form-group--error': $v.account.pgeGasSAID.$error,
                            }"
                          >
                            <label class="form__label"
                              >PG&amp;E Gas SAID<span class="r">*</span></label
                            >
                            <input
                              class="form__input"
                              type="text"
                              v-model="$v.account.pgeGasSAID.$model"
                            />
                          </div>
                          <div
                            class="error"
                            v-if="
                              $v.account.pgeGasSAID.$error &&
                              !$v.account.pgeGasSAID.required
                            "
                          >
                            * Required
                          </div>

                          <div
                            class="form-group"
                            :class="{
                              'form-group--error':
                                $v.account.customerPhone.$error,
                            }"
                          >
                            <label class="form__label"
                              >Customer Phone Number<span class="r"
                                >*</span
                              ></label
                            >
                            <input
                              class="form__input"
                              type="text"
                              v-model="$v.account.customerPhone.$model"
                            />
                          </div>
                          <div
                            class="error"
                            v-if="
                              $v.account.customerPhone.$error &&
                              !$v.account.customerPhone.required
                            "
                          >
                            * Required
                          </div>

                          <div
                            class="form-group"
                            :class="{
                              'form-group--error': $v.account.language.$error,
                            }"
                          >
                            <label class="form__label"
                              >Primary Language<span class="r">*</span></label
                            >
                            <select
                              class="form__input"
                              v-model="$v.account.language.$model"
                              required
                            >
                              <option value="" default selected hidden>
                                Select Any
                              </option>
                              <option value="english">English</option>
                            </select>
                          </div>
                          <div
                            class="error"
                            v-if="
                              $v.account.language.$error &&
                              !$v.account.language.required
                            "
                          >
                            * Required
                          </div>
                        </div>
                        <div>
                          <div
                            class="form-group"
                            :class="{
                              'form-group--error':
                                $v.account.customerName.$error,
                            }"
                          >
                            <label class="form__label"
                              >Customer Name On Utility Account<span class="r"
                                >*</span
                              ></label
                            >
                            <input
                              class="form__input"
                              type="text"
                              v-model="$v.account.customerName.$model"
                            />
                          </div>
                          <div
                            class="error"
                            v-if="
                              $v.account.customerName.$error &&
                              !$v.account.customerName.required
                            "
                          >
                            * Required
                          </div>
                          <div
                            class="form-group"
                            :class="{
                              'form-group--error':
                                $v.account.pgeElectricSAID.$error,
                            }"
                          >
                            <label class="form__label"
                              >PG&amp;E Electric SAID<span class="r"
                                >*</span
                              ></label
                            >
                            <input
                              class="form__input"
                              type="text"
                              v-model="$v.account.pgeElectricSAID.$model"
                            />
                          </div>
                          <div
                            class="error"
                            v-if="
                              $v.account.pgeElectricSAID.$error &&
                              !$v.account.pgeElectricSAID.required
                            "
                          >
                            * Required
                          </div>
                          <div
                            class="form-group"
                            :class="{
                              'form-group--error':
                                $v.account.customerEmail.$error,
                            }"
                          >
                            <label class="form__label"
                              >Customer Email Address<span class="r"
                                >*</span
                              ></label
                            >
                            <input
                              class="form__input"
                              type="text"
                              v-model="$v.account.customerEmail.$model"
                            />
                          </div>
                          <div
                            class="error"
                            v-if="
                              $v.account.customerEmail.$error &&
                              !$v.account.customerEmail.required
                            "
                          >
                            * Required
                          </div>
                          <div class="form-group">
                            <label class="form__label"
                              >Household Gross Annual Income</label
                            >
                            <select
                              name="householdGrossIncome"
                              class="form__input"
                              v-model="account.householdGrossIncome"
                            >
                              <option value="" default selected hidden>
                                Select Any
                              </option>
                              <option value="100k">$100K+</option>
                            </select>
                          </div>
                        </div>
                      </div>
                    </div>
                  </div>
                  <input type="submit" value="Submit Normal" />
                </form>
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
  },
  methods: {
    handleSubmit() {
      this.$v.$touch()
      if (this.$v.$invalid) {
        alert('form incomplete')
      } else {
        let myForm = document.getElementById('mainform')
        let formData = new FormData(myForm)
        fetch('/submit', {
          method: 'POST',
          headers: { 'Content-Type': 'application/x-www-form-urlencoded' },
          body: new URLSearchParams(formData).toString(),
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
  margin-bottom: 40px;
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
</style>
