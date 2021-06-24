<template>
  <div class="heatpump-info">
    <div class="grid grid-cols-1 md:grid-cols-2 gap-x-4">
      <div>
        <div
          class="form-group"
          :class="{
            'form-group--error': validator.heatpump.dateInstalled.$error,
          }"
        >
          <label class="form__label"
            >Date Installed<span class="r">*</span></label
          >
          <input
            class="form__input"
            type="text"
            name="heatpump.dateInstalled"
            v-model="validator.heatpump.dateInstalled.$model"
          />
        </div>
        <div
          class="error"
          v-if="
            validator.heatpump.dateInstalled.$error &&
            !validator.heatpump.dateInstalled.required
          "
        >
          * Required
        </div>
      </div>
      <div>
        <div
          class="form-group"
          :class="{
            'form-group--error': validator.heatpump.existingFuelType.$error,
          }"
        >
          <label class="form__label"
            >Existing Heating System Fuel Type<span class="r">*</span></label
          >
          <select v-model="validator.heatpump.existingFuelType.$model" required>
            <option value="" default selected hidden>Select Any</option>
            <option value="natural-gas">Natural Gas</option>
            <option value="propane">Propane</option>
            <option value="electric">Electric</option>
          </select>
        </div>
        <div
          class="error"
          v-if="
            validator.heatpump.existingFuelType.$error &&
            !validator.heatpump.existingFuelType.required
          "
        >
          * Required
        </div>
      </div>
    </div>
    <div class="grid grid-cols-1 md:grid-cols-2 gap-x-4">
      <div>
        <div
          class="form-group"
          :class="{
            'form-group--error': validator.heatpump.ahriNumber.$error,
          }"
        >
          <label class="form__label">AHRI Number<span class="r">*</span></label>
          <input
            class="form__input"
            type="text"
            name="heatpump.ahriNumber"
            v-model="validator.heatpump.ahriNumber.$model"
          />
        </div>
        <div
          class="error"
          v-if="
            validator.heatpump.ahriNumber.$error &&
            !validator.heatpump.ahriNumber.required
          "
        >
          * Required
        </div>
      </div>
      <div>
        <div
          class="form-group"
          :class="{
            'form-group--error': validator.heatpump.newHpManufacturer.$error,
          }"
        >
          <label class="form__label"
            >New Heat Pump Manufacturer<span class="r">*</span></label
          >
          <input
            class="form__input"
            type="text"
            name="heatpump.newHpManufacturer"
            v-model="validator.heatpump.newHpManufacturer.$model"
          />
        </div>
        <div
          class="error"
          v-if="
            validator.heatpump.newHpManufacturer.$error &&
            !validator.heatpump.newHpManufacturer.required
          "
        >
          * Required
        </div>
      </div>
    </div>
    <div class="grid grid-cols-1 md:grid-cols-2 gap-x-4">
      <div>
        <div
          class="form-group"
          :class="{
            'form-group--error': validator.heatpump.newHpModel.$error,
          }"
        >
          <label class="form__label"
            >New Heat Pump Model<span class="r">*</span></label
          >
          <input
            class="form__input"
            type="text"
            name="heatpump.newHpModel"
            v-model="validator.heatpump.newHpModel.$model"
          />
        </div>
        <div
          class="error"
          v-if="
            validator.heatpump.newHpModel.$error &&
            !validator.heatpump.newHpModel.required
          "
        >
          * Required
        </div>
      </div>
      <div>
        <div
          class="form-group"
          :class="{
            'form-group--error': validator.heatpump.serial.$error,
          }"
        >
          <label class="form__label">Serial #<span class="r">*</span></label>
          <input
            class="form__input"
            type="text"
            name="heatpump.serial"
            v-model="validator.heatpump.serial.$model"
          />
        </div>
        <div
          class="error"
          v-if="
            validator.heatpump.serial.$error &&
            !validator.heatpump.serial.required
          "
        >
          * Required
        </div>
      </div>
    </div>
    <div class="grid grid-cols-1 md:grid-cols-2 gap-x-4">
      <div>
        <div
          class="form-group"
          :class="{
            'form-group--error': validator.heatpump.hpUnitsInstalled.$error,
          }"
        >
          <label class="form__label"
            ># HP Units Installed<span class="r">*</span></label
          >
          <input
            class="form__input"
            type="text"
            name="heatpump.hpUnitsInstalled"
            v-model="validator.heatpump.hpUnitsInstalled.$model"
          />
        </div>
        <div
          class="error"
          v-if="
            validator.heatpump.hpUnitsInstalled.$error &&
            !validator.heatpump.hpUnitsInstalled.required
          "
        >
          * Required
        </div>
      </div>
      <div>
        <div
          class="form-group"
          :class="{
            'form-group--error': validator.heatpump.hspfRating.$error,
          }"
        >
          <label class="form__label">HSPF Rating<span class="r">*</span></label>
          <input
            class="form__input"
            type="text"
            name="heatpump.hspfRating"
            v-model="validator.heatpump.hspfRating.$model"
          />
        </div>
        <div
          class="error"
          v-if="
            validator.heatpump.hspfRating.$error &&
            !validator.heatpump.hspfRating.required
          "
        >
          * Required
        </div>
      </div>
    </div>
    <div class="grid grid-cols-1 md:grid-cols-2 gap-x-4">
      <div>
        <div
          class="form-group"
          :class="{
            'form-group--error': validator.heatpump.seerRating.$error,
          }"
        >
          <label class="form__label">SEER Rating<span class="r">*</span></label>
          <input
            class="form__input"
            type="text"
            name="heatpump.seerRating"
            v-model="validator.heatpump.seerRating.$model"
          />
        </div>
        <div
          class="error"
          v-if="
            validator.heatpump.seerRating.$error &&
            !validator.heatpump.seerRating.required
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
              validator.heatpump.measureCostToCustomer.$error,
          }"
        >
          <label class="form__label"
            >Measure Cost to Customer<span class="r">*</span></label
          >
          <input
            class="form__input"
            type="text"
            name="heatpump.measureCostToCustomer"
            v-model="validator.heatpump.measureCostToCustomer.$model"
          />
        </div>
        <div
          class="error"
          v-if="
            validator.heatpump.measureCostToCustomer.$error &&
            !validator.heatpump.measureCostToCustomer.required
          "
        >
          * Required
        </div>
      </div>
    </div>
    <div class="grid grid-cols-1 md:grid-cols-2 gap-x-4">
      <div>
        <div
          class="form-group"
          :class="{
            'form-group--error': validator.heatpump.existingHeatType.$error,
          }"
        >
          <label class="form__label"
            >Existing Heating System Type<span class="r">*</span></label
          >
          <select v-model="validator.heatpump.existingHeatType.$model" required>
            <option value="" default selected hidden>Select Any</option>
            <option value="Gas Central or Package Furnace">
              Gas Central or Package Furnace
            </option>
            <option value="Gas Wall Furnance">Gas Wall Furnance</option>
            <option value="Gas Floor Furnance">Gas Floor Furnance</option>
            <option value="Electric Heat Pump">Electric Heat Pump</option>
            <option value="Electric Baseboard">Electric Baseboard</option>
          </select>
        </div>
        <div
          class="error"
          v-if="
            validator.heatpump.existingHeatType.$error &&
            !validator.heatpump.existingHeatType.required
          "
        >
          * Required
        </div>
      </div>
      <div>
        <div
          class="form-group"
          :class="{
            'form-group--error': validator.heatpump.existingHeatSize.$error,
          }"
        >
          <label class="form__label"
            >Existing Heating System Size (kBTU)<span class="r">*</span></label
          >
          <input
            class="form__input"
            type="text"
            name="heatpump.existingHeatSize"
            v-model="validator.heatpump.existingHeatSize.$model"
          />
        </div>
        <div
          class="error"
          v-if="
            validator.heatpump.existingHeatSize.$error &&
            !validator.heatpump.existingHeatSize.required
          "
        >
          * Required
        </div>
      </div>
    </div>
    <div class="grid grid-cols-1 md:grid-cols-2 gap-x-4">
      <div>
        <div
          class="form-group"
          :class="{
            'form-group--error': validator.heatpump.existingCoolingType.$error,
          }"
        >
          <label class="form__label"
            >Existing Cooling System Type<span class="r">*</span></label
          >
          <select
            v-model="validator.heatpump.existingCoolingType.$model"
            required
          >
            <option value="" default selected hidden>Select Any</option>
            <option value="Central Split or Packaged">
              Central Split or Packaged
            </option>
            <option value="Window AC">Window AC</option>
            <option value="Wall AC">Wall AC</option>
            <option value="No Existing AC">No Existing AC</option>
          </select>
        </div>
        <div
          class="error"
          v-if="
            validator.heatpump.existingCoolingType.$error &&
            !validator.heatpump.existingCoolingType.required
          "
        >
          * Required
        </div>
      </div>
      <div>
        <div
          class="form-group"
          :class="{
            'form-group--error': validator.heatpump.existingCoolingSize.$error,
          }"
        >
          <label class="form__label"
            >Existing Cooling System Size (Tons)<span class="r">*</span></label
          >
          <input
            class="form__input"
            type="text"
            name="heatpump.existingCoolingSize"
            v-model="validator.heatpump.existingCoolingSize.$model"
          />
        </div>
        <div
          class="error"
          v-if="
            validator.heatpump.existingCoolingSize.$error &&
            !validator.heatpump.existingCoolingSize.required
          "
        >
          * Required
        </div>
      </div>
    </div>
    <div class="grid grid-cols-1 md:grid-cols-2 gap-x-4">
      <div>
        <div
          class="form-group"
          :class="{
            'form-group--error': validator.heatpump.newPumpType.$error,
          }"
        >
          <label class="form__label"
            >New Heat Pump System Type<span class="r">*</span></label
          >
          <select v-model="validator.heatpump.newPumpType.$model" required>
            <option value="" default selected hidden>Select Any</option>
            <option value="Standard (DX) Heat Pump">
              Standard (DX) Heat Pump
            </option>
            <option value="Ductless Minisplit Heat Pump">
              Ductless Minisplit Heat Pump
            </option>
            <option value="Ducted Minisplit Heat Pump">
              Ducted Minisplit Heat Pump
            </option>
          </select>
        </div>
        <div
          class="error"
          v-if="
            validator.heatpump.newPumpType.$error &&
            !validator.heatpump.newPumpType.required
          "
        >
          * Required
        </div>
      </div>
      <div>
        <div
          class="form-group"
          :class="{
            'form-group--error': validator.heatpump.newPumpSize.$error,
          }"
        >
          <label class="form__label"
            >New Heat Pump Size (Tons)<span class="r">*</span></label
          >
          <input
            class="form__input"
            type="text"
            name="heatpump.newPumpSize"
            v-model="validator.heatpump.newPumpSize.$model"
          />
        </div>
        <div
          class="error"
          v-if="
            validator.heatpump.newPumpSize.$error &&
            !validator.heatpump.newPumpSize.required
          "
        >
          * Required
        </div>
      </div>
    </div>
    <div class="grid grid-cols-1 md:grid-cols-2 gap-x-4">
      <div>
        <div
          class="form-group"
          :class="{
            'form-group--error': validator.heatpump.proofOfPermitClosure.$error,
          }"
        >
          <label class="form__label"
            >Proof of Permit Closure<span class="r">*</span></label
          >
          <FormsUploadButton
            v-model="validator.heatpump.proofOfPermitClosure.$model"
          />
        </div>
        <div
          class="error"
          v-if="
            validator.heatpump.proofOfPermitClosure.$error &&
            !validator.heatpump.proofOfPermitClosure.required
          "
        >
          * Required
        </div>
      </div>
      <div>
        <div
          class="form-group"
          :class="{
            'form-group--error': validator.heatpump.casSheet.$error,
          }"
        >
          <label class="form__label">CAS sheet<span class="r">*</span></label>

          <FormsUploadButton v-model="validator.heatpump.casSheet.$model" />
        </div>
        <div
          class="error"
          v-if="
            validator.heatpump.casSheet.$error &&
            !validator.heatpump.casSheet.required
          "
        >
          * Required
        </div>
      </div>
    </div>
    <div class="grid grid-cols-1 md:grid-cols-2 gap-x-4">
      <div>
        <div
          class="form-group"
          :class="{
            'form-group--error': validator.heatpump.photoOld.$error,
          }"
        >
          <label class="form__label"
            >Photo of Existing Equipment<span class="r">*</span></label
          >
          <FormsUploadButton v-model="validator.heatpump.photoOld.$model" />
        </div>
        <div
          class="error"
          v-if="
            validator.heatpump.photoOld.$error &&
            !validator.heatpump.photoOld.required
          "
        >
          * Required
        </div>
      </div>
      <div>
        <div
          class="form-group"
          :class="{
            'form-group--error': validator.heatpump.photoNew.$error,
          }"
        >
          <label class="form__label"
            >Photo of New Equipment<span class="r">*</span></label
          >

          <FormsUploadButton v-model="validator.heatpump.photoNew.$model" />
        </div>
        <div
          class="error"
          v-if="
            validator.heatpump.photoNew.$error &&
            !validator.heatpump.photoNew.required
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
  props: ['heatpump', 'validator'],
}
</script>
