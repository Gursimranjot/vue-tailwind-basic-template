<template>
    <div class="form__group">
        <label for="">{{placeholderText}}</label>
        <input
            :type="inputType" 
            :placeholder="placeholderText" 
            v-model="inputValue"
            :required="required"
            class="input">
            <span class="error-message">{{ errorMessage }}</span>
    </div>
</template>

<script>
export default {
    props:{
        inputType:[String,Number],
        value:[String,Number, Array],
        placeholderText:String,
        required: Boolean,
        errorMessage: String
    },
    data(){
        return{
            inputValue: this.value
        }
    },
    watch:{
        value(){
             this.inputValue = this.value;
        }
    },
    methods:{
        changeText(){
            this.$emit('input', this.inputValue, )
        }
    }
}
</script>

<style lang="sass" scoped>
.form__group
    margin-bottom: 1.5625rem
    width: 100%
    position: relative
    label
        display: inline-block
        font-weight: 500
        margin-bottom: 0.4rem
    .error-message
      position: absolute
      top: 2px
      right: 0
      font-size: 13px
      overflow: hidden
      white-space: nowrap
      text-overflow: ellipsis
      max-width: calc(100% - 120px)
.input-form
    width: 100%
.input
    box-sizing: border-box
    border: solid 1px red
    border-radius: 5px
    padding: 0.5em 1em
    width: 100%
    color: #000
    font-size: inherit
    letter-spacing: 1px
    min-height: 3em
    &::placeholder
      color: #bbb
    &:focus
        outline: none
.input-upload
 .input
   border: 1px dashed #0566A5;
   background: rgba(5, 102, 165, 0.06);
</style>