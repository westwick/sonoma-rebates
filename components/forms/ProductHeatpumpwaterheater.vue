<template>
  <div class="heatpump-info">
    <div class="grid grid-cols-2 gap-x-4">
      <div>
        <div
          class="form-group"
          :class="{
            'form-group--error':
              validator.heatpumpwaterheater.dateInstalled.$error,
          }"
        >
          <label class="form__label"
            >Date Installed<span class="r">*</span></label
          >
          <input
            class="form__input"
            type="text"
            name="heatpumpwaterheater.dateInstalled"
            v-model="validator.heatpumpwaterheater.dateInstalled.$model"
          />
        </div>
        <div
          class="error"
          v-if="
            validator.heatpumpwaterheater.dateInstalled.$error &&
            !validator.heatpumpwaterheater.dateInstalled.required
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
              validator.heatpumpwaterheater.existingWaterHeaterFuelType.$error,
          }"
        >
          <label class="form__label"
            >Existing Water Heater Fuel Type<span class="r">*</span></label
          >

          <select
            v-model="
              validator.heatpumpwaterheater.existingWaterHeaterFuelType.$model
            "
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
            validator.heatpumpwaterheater.existingWaterHeaterFuelType.$error &&
            !validator.heatpumpwaterheater.existingWaterHeaterFuelType.required
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
              validator.heatpumpwaterheater.newHpwhMake.$error,
          }"
        >
          <label class="form__label"
            >New HPWH Make<span class="r">*</span></label
          >
          <select
            v-model="validator.heatpumpwaterheater.newHpwhMake.$model"
            required
          >
            <option value="" default selected hidden>Select Any</option>
            <option value="Rheem">Rheem</option>
            <option value="AO Smith">AO Smith</option>
          </select>
        </div>
        <div
          class="error"
          v-if="
            validator.heatpumpwaterheater.newHpwhMake.$error &&
            !validator.heatpumpwaterheater.newHpwhMake.required
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
              validator.heatpumpwaterheater.newHpwhModel.$error,
          }"
        >
          <label class="form__label"
            >New HPWH Model<span class="r">*</span></label
          >
          <input
            class="form__input"
            type="text"
            name="heatpumpwaterheater.newHpwhModel"
            v-model="validator.heatpumpwaterheater.newHpwhModel.$model"
          />
        </div>
        <div
          class="error"
          v-if="
            validator.heatpumpwaterheater.newHpwhModel.$error &&
            !validator.heatpumpwaterheater.newHpwhModel.required
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
              validator.heatpumpwaterheater.newHpwhTankSize.$error,
          }"
        >
          <label class="form__label"
            >New HPWH Tank Size (gals)<span class="r">*</span></label
          >
          <input
            class="form__input"
            type="text"
            name="heatpumpwaterheater.newHpwhTankSize"
            v-model="validator.heatpumpwaterheater.newHpwhTankSize.$model"
          />
        </div>
        <div
          class="error"
          v-if="
            validator.heatpumpwaterheater.newHpwhTankSize.$error &&
            !validator.heatpumpwaterheater.newHpwhTankSize.required
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
              validator.heatpumpwaterheater.newHpwhEfficiencyFactory.$error,
          }"
        >
          <label class="form__label"
            >New HPWH Efficiency Factor (UEF)<span class="r">*</span></label
          >

          <input
            class="form__input"
            type="text"
            name="heatpumpwaterheater.newHpwhTankSize"
            v-model="
              validator.heatpumpwaterheater.newHpwhEfficiencyFactory.$model
            "
          />
        </div>
        <div
          class="error"
          v-if="
            validator.heatpumpwaterheater.newHpwhEfficiencyFactory.$error &&
            !validator.heatpumpwaterheater.newHpwhEfficiencyFactory.required
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
              validator.heatpumpwaterheater.wifiEnabled.$error,
          }"
        >
          <label class="form__label"
            >Wi-Fi or DR enabled?<span class="r">*</span></label
          >
          <select
            v-model="validator.heatpumpwaterheater.wifiEnabled.$model"
            required
          >
            <option value="" default selected hidden>Select Any</option>
            <option value="yes">Yes</option>
            <option value="no">No</option>
          </select>
        </div>
        <div
          class="error"
          v-if="
            validator.heatpumpwaterheater.wifiEnabled.$error &&
            !validator.heatpumpwaterheater.wifiEnabled.required
          "
        >
          * Required
        </div>
      </div>
      <div>
        <div
          class="form-group"
          :class="{
            'form-group--error': validator.heatpumpwaterheater.macIdOrSn.$error,
          }"
        >
          <label class="form__label"
            >MAC ID or SN#<span class="r">*</span></label
          >

          <input
            class="form__input"
            type="text"
            name="heatpumpwaterheater.newHpwhTankSize"
            v-model="validator.heatpumpwaterheater.macIdOrSn.$model"
          />
        </div>
        <div
          class="error"
          v-if="
            validator.heatpumpwaterheater.macIdOrSn.$error &&
            !validator.heatpumpwaterheater.macIdOrSn.required
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
              validator.heatpumpwaterheater.thermostaticMixingValve.$error,
          }"
        >
          <label class="form__label"
            >Thermostatic Mixing Valve installed?<span class="r">*</span></label
          >
          <select
            v-model="
              validator.heatpumpwaterheater.thermostaticMixingValve.$model
            "
            required
          >
            <option value="" default selected hidden>Select Any</option>
            <option value="yes">Yes</option>
            <option value="no">No</option>
          </select>
        </div>
        <div
          class="error"
          v-if="
            validator.heatpumpwaterheater.thermostaticMixingValve.$error &&
            !validator.heatpumpwaterheater.thermostaticMixingValve.required
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
              validator.heatpumpwaterheater.measureCostToCustomer.$error,
          }"
        >
          <label class="form__label"
            >Measure Cost to Customer<span class="r">*</span></label
          >

          <input
            class="form__input"
            type="text"
            name="heatpumpwaterheater.newHpwhTankSize"
            v-model="validator.heatpumpwaterheater.measureCostToCustomer.$model"
          />
        </div>
        <div
          class="error"
          v-if="
            validator.heatpumpwaterheater.measureCostToCustomer.$error &&
            !validator.heatpumpwaterheater.measureCostToCustomer.required
          "
        >
          * Required
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  props: ['heatpumpwaterheater', 'validator'],
}
</script>
