<template>
  <div class="b-base-upload-button">
    <form
      class="b-base-upload__inner"
    >
      <input
        style="display: none;"
        type="file"
        accept="image/*"
        ref="uploadInput"
        @change="onUploadClick"
      />
      <BaseLoading
        v-if="progress"
      />
      <BaseButton
        v-if="!progress"
        @click.prevent="upload"
        :color="palette ? 'main-green-transparent' : 'main-green'"
        :size="palette ? 'small' : 'middle'"
      >
        <template v-if="!palette">
          Upload an image
        </template>
        <template v-else>
          New image
        </template>
      </BaseButton>
    </form>
  </div>
</template>

<script>
import api from '@store/api'

export default {
  model: {
    prop: 'value',
    event: 'upload'
  },

  props: {
    progress: Boolean,
    palette: {
      type: Array,
      default: null
    }
  },

  methods: {
    onUploadClick (event) {
      this.$emit('startProgress', true)
      this.uploadFile(event)
    },

    upload () {
      this.$refs.uploadInput.click()
    },

    uploadFile (event) {
      this.$emit('upload', api.uploadFileAfterClickButton(event))
    }

  }
}
</script>

<style lang="sass" scoped>
@import '../../assets/sass/_variables.sass'

.b-base-upload-button
  width: 100%

  display: flex
  align-items: center
  justify-content: center

</style>
