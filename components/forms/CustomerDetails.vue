<template>
  <div class="customer-details">
    <div class="bg-gray-100 p-8">
      <p class="form-section-name mb-8">Account Information</p>
      <div class="grid grid-cols-2 gap-x-8">
        <div>
          <div
            class="form-group"
            :class="{
              'form-group--error': validator.account.pgeAccountNum.$error,
            }"
          >
            <label class="form__label"
              >PG&amp;E Account #<span class="r">*</span></label
            >
            <input
              class="form__input"
              type="text"
              name="account.pgeAccountNum"
              v-model="validator.account.pgeAccountNum.$model"
            />
          </div>
          <div
            class="error"
            v-if="
              validator.account.pgeAccountNum.$error &&
              !validator.account.pgeAccountNum.required
            "
          >
            * Required
          </div>

          <div
            class="form-group"
            :class="{
              'form-group--error': validator.account.pgeGasSAID.$error,
            }"
          >
            <label class="form__label"
              >PG&amp;E Gas SAID<span class="r">*</span></label
            >
            <input
              class="form__input"
              type="text"
              name="account.pgeGasSAID"
              v-model="validator.account.pgeGasSAID.$model"
            />
          </div>
          <div
            class="error"
            v-if="
              validator.account.pgeGasSAID.$error &&
              !validator.account.pgeGasSAID.required
            "
          >
            * Required
          </div>

          <div
            class="form-group"
            :class="{
              'form-group--error': validator.account.customerPhone.$error,
            }"
          >
            <label class="form__label"
              >Customer Phone Number<span class="r">*</span></label
            >
            <input
              class="form__input"
              type="text"
              name="account.customerPhone"
              v-model="validator.account.customerPhone.$model"
            />
          </div>
          <div
            class="error"
            v-if="
              validator.account.customerPhone.$error &&
              !validator.account.customerPhone.required
            "
          >
            * Required
          </div>

          <div
            class="form-group"
            :class="{
              'form-group--error': validator.account.language.$error,
            }"
          >
            <label class="form__label"
              >Primary Language<span class="r">*</span></label
            >
            <select
              class="form__input"
              name="account.language"
              v-model="validator.account.language.$model"
              required
            >
              <option value="" default selected hidden>Select Any</option>
              <option value="english">English</option>
            </select>
          </div>
          <div
            class="error"
            v-if="
              validator.account.language.$error &&
              !validator.account.language.required
            "
          >
            * Required
          </div>
        </div>
        <div>
          <div
            class="form-group"
            :class="{
              'form-group--error': validator.account.customerName.$error,
            }"
          >
            <label class="form__label"
              >Customer Name On Utility Account<span class="r">*</span></label
            >
            <input
              class="form__input"
              type="text"
              name="account.customerName"
              v-model="validator.account.customerName.$model"
            />
          </div>
          <div
            class="error"
            v-if="
              validator.account.customerName.$error &&
              !validator.account.customerName.required
            "
          >
            * Required
          </div>
          <div
            class="form-group"
            :class="{
              'form-group--error': validator.account.pgeElectricSAID.$error,
            }"
          >
            <label class="form__label"
              >PG&amp;E Electric SAID<span class="r">*</span></label
            >
            <input
              class="form__input"
              type="text"
              name="account.pgeElectricSAID"
              v-model="validator.account.pgeElectricSAID.$model"
            />
          </div>
          <div
            class="error"
            v-if="
              validator.account.pgeElectricSAID.$error &&
              !validator.account.pgeElectricSAID.required
            "
          >
            * Required
          </div>
          <div
            class="form-group"
            :class="{
              'form-group--error': validator.account.customerEmail.$error,
            }"
          >
            <label class="form__label"
              >Customer Email Address<span class="r">*</span></label
            >
            <input
              class="form__input"
              type="text"
              name="account.customerEmail"
              v-model="validator.account.customerEmail.$model"
            />
          </div>
          <div
            class="error"
            v-if="
              validator.account.customerEmail.$error &&
              !validator.account.customerEmail.required
            "
          >
            * Required
          </div>
          <div class="form-group">
            <label class="form__label">Household Gross Annual Income</label>
            <select
              name="account.householdGrossIncome"
              class="form__input"
              v-model="account.householdGrossIncome"
            >
              <option value="" default selected hidden>Select Any</option>
              <option value="100k">$100K+</option>
            </select>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  props: ['account', 'validator'],
}
</script>
