<!-- *************************************************************************

This File will be used to input field

************************************************************************* -->

<template>
  <div v-show="!hide">
    <input
      :id="id"
      v-model="value"
      :name="name"
      :type="type"
      :placeholder="placeholder"
      :tabindex="tabindex"
      :class="classname"
      :autocomplete="autocomplete"
      :maxlength="maxlength"
      :disabled="disabled"
      @focus="onFocus($event)"
      @input="onChangefield($event)"
      @blur="onBlur($event)"
      @keypress="onKeyPrees($event)"
      @keydown="onKeyDown($event)"
      @keyup="onKeyUp($event)
    />
  </div>
</template>

<!-- *************************************************************************

SCRIPT

************************************************************************* -->

<script>
import * as Regex from './regex'

export default {
  props: {
    id: String, // Id of the component
    name: String, // Name of the component
    tabindex:  {  // Tab index of the component
        type:Number,
        default:0
    },
    placeholder: String, // Place holder of the component
    hide: Boolean, // To hide or show the component
    disabled: Boolean, // When present, it specifies that the component should be disabled.
    type: {
      type: String,
      default: 'text',
    },
    value: String, // value of the component
    maxlength: {  // Max Length of the component
        type:Number,
        default:25
    }, 
    isNumberOnly: Boolean, // Allow only number,
    regex:{
        type:RegExp,
        default:Regex.TEXT_REGEX
    }
    autocomplete:{ // autocomplete value
      type:String
      default:''
    },
    classname::Object  // Add input class
  },
  methods: {
    /**
     *  On change event of input field
     */
    onChangefield() {
      if (this.isNumberOnly) {
        this.value = this.value.replace(Regex.ONLY_NUMBERS_REGEX, '')
      } else {
        if (this.value.trim().length === 0) {
          this.value = this.value.trim()
        } else {
          let regex = this.regex
            this.value = this.value.replace(regex, '')
        }
      }
      this.$emit('change',event , this.value)
    },
    /**
     *  On blur event of input field
     */
    onBlur(event) {
     this.$emit('blur',event)
    },
    /** On Focus event of input field */
    onFocus(event){
        this.$emit('focus',event)
    },
    /** On Key press event of input field */
    onKeyPrees(event){
        this.$emit('keypress',event)
    },
    /** On Key down event of input field */
    onKeyDown(event){
        this.$emit('keydown',event)
    },
    /** On key Up event of input field */
    onKeyUp(event){
      this.$emit('keyup',event)
    }
  },
}
</script>
