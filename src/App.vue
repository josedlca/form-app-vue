<template>
  <div id="app">
    <Wrapper
      group="update-form"
      v-cloak
    >
        <div slot-scope="props">
            <fieldset class="fieldset">
                <legend>Personal details</legend>

                <div>
                    <TextInput
                      :group="props.group"
                      name="first_name"
                      v-model="props.fields.first_name"
                      :focus="true"
                      placeholder="First name"
                      maxlength="9"
                      autocomplete="given-name"
                    ></TextInput>
                </div>

            </fieldset>
        </div>
    </Wrapper>
  </div>
</template>

<script>
import Wrapper from './components/Form/Wrapper.vue'
import TextInput from './components/Form/Inputs/Text.vue'

export default {
  name: 'App',
  components: {
    Wrapper,
    TextInput
  }
}
</script>

<style>

</style>
