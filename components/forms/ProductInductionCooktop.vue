<template>
  <div class="heatpump-info">
    <div class="grid grid-cols-2 gap-x-4">
      <div>
        <div
          class="form-group"
          :class="{
            'form-group--error':
              validator.inductioncooktop.dateInstalled.$error,
          }"
        >
          <label class="form__label"
            >Date Installed<span class="r">*</span></label
          >
          <input
            class="form__input"
            type="text"
            name="inductioncooktop.dateInstalled"
            v-model="validator.inductioncooktop.dateInstalled.$model"
          />
        </div>
        <div
          class="error"
          v-if="
            validator.inductioncooktop.dateInstalled.$error &&
            !validator.inductioncooktop.dateInstalled.required
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
              validator.inductioncooktop.existingFuelType.$error,
          }"
        >
          <label class="form__label"
            >Existing Cooktop or Range Fuel Type<span class="r">*</span></label
          >

          <select
            v-model="validator.inductioncooktop.existingFuelType.$model"
            required
          >
            <option value="" default selected hidden>Select Any</option>
            <option value="natural-gas">Natural Gas</option>
            <option value="propane">Propane</option>
            <option value="electric">Electric</option>
          </select>
        </div>
        <div
          class="error"
          v-if="
            validator.inductioncooktop.existingFuelType.$error &&
            !validator.inductioncooktop.existingFuelType.required
          "
        >
          * Required
        </div>
      </div>
    </div>
    <div class="grid grid-cols-2 gap-x-4">
      <div>
        <div
          class="form-group"
          :class="{
            'form-group--error':
              validator.inductioncooktop.existingApplianceType.$error,
          }"
        >
          <label class="form__label"
            >Existing Cooktop or Range Appliance Type<span class="r"
              >*</span
            ></label
          >
          <select
            v-model="validator.inductioncooktop.existingApplianceType.$model"
            required
          >
            <option value="" default selected hidden>Select Any</option>
            <option value="cooktop">Cooktop</option>
            <option value="range">Range</option>
          </select>
        </div>
        <div
          class="error"
          v-if="
            validator.inductioncooktop.existingApplianceType.$error &&
            !validator.inductioncooktop.existingApplianceType.required
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
              validator.inductioncooktop.newApplianceType.$error,
          }"
        >
          <label class="form__label"
            >New Cooktop or Range Appliance Type<span class="r">*</span></label
          >
          <select
            v-model="validator.inductioncooktop.newApplianceType.$model"
            required
          >
            <option value="" default selected hidden>Select Any</option>
            <option value="cooktop">Cooktop</option>
            <option value="range">Range</option>
          </select>
        </div>
        <div
          class="error"
          v-if="
            validator.inductioncooktop.newApplianceType.$error &&
            !validator.inductioncooktop.newApplianceType.required
          "
        >
          * Required
        </div>
      </div>
    </div>
    <div class="grid grid-cols-2 gap-x-4">
      <div>
        <div
          class="form-group"
          :class="{
            'form-group--error':
              validator.inductioncooktop.connectedLoad.$error,
          }"
        >
          <label class="form__label"
            >Connected Load (kW Rating)<span class="r">*</span></label
          >
          <input
            class="form__input"
            type="text"
            name="inductioncooktop.connectedLoad"
            v-model="validator.inductioncooktop.connectedLoad.$model"
          />
        </div>
        <div
          class="error"
          v-if="
            validator.inductioncooktop.connectedLoad.$error &&
            !validator.inductioncooktop.connectedLoad.required
          "
        >
          * Required
        </div>
      </div>
      <div>
        <div
          class="form-group"
          :class="{
            'form-group--error': validator.inductioncooktop.manufacturer.$error,
          }"
        >
          <label class="form__label"
            >Manufacturer<span class="r">*</span></label
          >

          <input
            class="form__input"
            type="text"
            name="inductioncooktop.newHpwhTankSize"
            v-model="validator.inductioncooktop.manufacturer.$model"
          />
        </div>
        <div
          class="error"
          v-if="
            validator.inductioncooktop.manufacturer.$error &&
            !validator.inductioncooktop.manufacturer.required
          "
        >
          * Required
        </div>
      </div>
    </div>
    <div class="grid grid-cols-2 gap-x-4">
      <div>
        <div
          class="form-group"
          :class="{
            'form-group--error': validator.inductioncooktop.model.$error,
          }"
        >
          <label class="form__label">Model<span class="r">*</span></label>
          <input
            class="form__input"
            type="text"
            name="inductioncooktop.newHpwhTankSize"
            v-model="validator.inductioncooktop.model.$model"
          />
        </div>
        <div
          class="error"
          v-if="
            validator.inductioncooktop.model.$error &&
            !validator.inductioncooktop.model.required
          "
        >
          * Required
        </div>
      </div>
      <div>
        <!-- intentionally left empty -->
      </div>
    </div>
  </div>
</template>

<script>
export default {
  props: ['inductioncooktop', 'validator'],
}
</script>
