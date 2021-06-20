<template>
  <div class="mailing-address">
    <div class="bg-gray-100 p-8">
      <p class="form-section-name mb-8">Account Mailing Address</p>
      <div
        class="form-group"
        :class="{
          'form-group--error': validator.mailingAddress.street.$error,
        }"
      >
        <label class="form__label"
          >Street Address<span class="r">*</span></label
        >
        <input
          class="form__input"
          type="text"
          name="mailingAddress.street"
          v-model="validator.mailingAddress.street.$model"
        />
      </div>
      <div
        class="error"
        v-if="
          validator.mailingAddress.street.$error &&
          !validator.mailingAddress.street.required
        "
      >
        * Required
      </div>
      <div class="grid grid-cols-3 gap-x-8">
        <div>
          <div
            class="form-group"
            :class="{
              'form-group--error': validator.mailingAddress.city.$error,
            }"
          >
            <label class="form__label">City<span class="r">*</span></label>
            <input
              class="form__input"
              type="text"
              name="mailingAddress.city"
              v-model="validator.mailingAddress.city.$model"
            />
          </div>
          <div
            class="error"
            v-if="
              validator.mailingAddress.city.$error &&
              !validator.mailingAddress.city.required
            "
          >
            * Required
          </div>
        </div>
        <div>
          <div
            class="form-group"
            :class="{
              'form-group--error': validator.mailingAddress.state.$error,
            }"
          >
            <label class="form__label">State<span class="r">*</span></label>
            <input
              class="form__input"
              type="text"
              name="mailingAddress.state"
              v-model="validator.mailingAddress.state.$model"
            />
          </div>
          <div
            class="error"
            v-if="
              validator.mailingAddress.state.$error &&
              !validator.mailingAddress.state.required
            "
          >
            * Required
          </div>
        </div>
        <div>
          <div
            class="form-group"
            :class="{
              'form-group--error': validator.mailingAddress.zip.$error,
            }"
          >
            <label class="form__label">Zip<span class="r">*</span></label>
            <input
              class="form__input"
              type="text"
              name="mailingAddress.zip"
              v-model="validator.mailingAddress.zip.$model"
            />
          </div>
          <div
            class="error"
            v-if="
              validator.mailingAddress.zip.$error &&
              !validator.mailingAddress.zip.required
            "
          >
            * Required
          </div>
        </div>
      </div>

      <p class="form-section-name mb-4 mt-8">Payment</p>
      <div
        class="form-group"
        :class="{
          'form-group--error':
            validator.mailingAddress.installingContractor.$error,
        }"
      >
        <label class="form__label"
          >Installing Contractor<span class="r">*</span></label
        >
        <p class="label-hint mb-2">
          For "Induction Cooktop/Stove" measure, can enter "Self-Install".
        </p>
        <input
          class="form__input"
          type="text"
          name="mailingAddress.installingContractor"
          v-model="validator.mailingAddress.installingContractor.$model"
        />
      </div>
      <div
        class="error"
        v-if="
          validator.mailingAddress.installingContractor.$error &&
          !validator.mailingAddress.installingContractor.required
        "
      >
        * Required
      </div>
      <div class="grid grid-cols-2 gap-x-8">
        <div>
          <div
            class="form-group"
            :class="{
              'form-group--error': validator.mailingAddress.rebatePayee.$error,
            }"
          >
            <label class="form__label"
              >Rebate Payee<span class="r">*</span></label
            >
            <input
              class="form__input"
              type="text"
              name="mailingAddress.rebatePayee"
              v-model="validator.mailingAddress.rebatePayee.$model"
            />
          </div>
          <div
            class="error"
            v-if="
              validator.mailingAddress.rebatePayee.$error &&
              !validator.mailingAddress.rebatePayee.required
            "
          >
            * Required
          </div>
        </div>
        <div>
          <div
            class="form-group"
            :class="{
              'form-group--error': validator.mailingAddress.whereToSend.$error,
            }"
          >
            <label class="form__label"
              >Where do you want to send this rebate?<span class="r"
                >*</span
              ></label
            >
            <input
              class="form__input"
              type="text"
              name="mailingAddress.whereToSend"
              v-model="validator.mailingAddress.whereToSend.$model"
            />
          </div>
          <div
            class="error"
            v-if="
              validator.mailingAddress.whereToSend.$error &&
              !validator.mailingAddress.whereToSend.required
            "
          >
            * Required
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  props: ['mailingAddress', 'validator'],
}
</script>
