<i18n>
{
  "ru": {
    "days": "Дней",
    "hours": "Часов",
    "minutes": "Минут",
    "seconds": "Секунд"
  },
  "en": {
    "days": "Days",
    "hours": "Hours",
    "minutes": "Minutes",
    "seconds": "Seconds"
  },
  "de": {
    "days": "Tage",
    "hours": "Stunden",
    "minutes": "Minuten",
    "seconds": "Sekunden"
  }
}
</i18n>

<template>
<table
    class="b-timer is-editable js-timer b-border"
    :data-timestamp="timer.timestamp"
    :data-utc-offset="timer.UTC"
    :path="path"
    :style="[objVarsMedia, objVarsTypo]"
    @mouseleave="mouseleave"
    @mouseover.stop="mouseover"
  >

  <thead v-show="labels.show && labels.position === 'top'" class="b-timer__labels">
    <tr>
      <td class="label">{{ $t('days') }}</td>
      <td class="label-divider"></td>
      <td class="label">{{ $t('hours') }}</td>
      <td class="label-divider"></td>
      <td class="label">{{ $t('minutes') }}</td>
      <td class="label-divider"></td>
      <td class="label">{{ $t('seconds') }}</td>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td class="number js-timer-days" :style="{ 'background-color' : timer.colorTile }">{{ parse(days) | check }}</td>
      <td class="number-divider"></td>
      <td class="number js-timer-hours" :style="{ 'background-color' : timer.colorTile }">{{ parse(hours, 24) | check }}</td>
      <td class="number-divider"></td>
      <td class="number js-timer-minutes" :style="{ 'background-color' : timer.colorTile }">{{ parse(minutes, 60) | check }}</td>
      <td class="number-divider"></td>
      <td class="number js-timer-seconds" :style="{ 'background-color' : timer.colorTile }">{{ parse(seconds, 60) | check }}</td>
    </tr>
  </tbody>

  <tfoot v-show="labels.show && labels.position === 'bottom'" class="b-timer__labels">
    <tr>
      <td class="label">{{ $t('days') }}</td>
      <td class="label-divider"></td>
      <td class="label">{{ $t('hours') }}</td>
      <td class="label-divider"></td>
      <td class="label">{{ $t('minutes') }}</td>
      <td class="label-divider"></td>
      <td class="label">{{ $t('seconds') }}</td>
    </tr>
  </tfoot>

</table>
</template>

<script>
import elementMedia from '../mixins/elementMedia'
import elementHover from '../mixins/elementHover'

export default {
  name: 'Timer',

  mixins: [
    elementMedia,
    elementHover
  ],

  filters: {
    check: function (value) {
      if (value && value > 0) {
        if (value.toString().length < 2) {
          return '0' + value
        } else {
          return value
        }
      } else {
        return '00'
      }
    }
  },

  props: {
    path: {
      type: String,
      required: true,
      validator: value => typeof value === 'string'
    }
  },

  data () {
    return {
      timeLeft: null,
      interval: null
    }
  },

  computed: {
    timer () {
      return this.$section.get(`$sectionData.${ this.path }.timer`)
    },

    labels () {
      return this.timer.labels
    },

    seconds () {
      return this.timeLeft / 1000
    },

    minutes () {
      return this.seconds / 60
    },

    hours () {
      return this.minutes / 60
    },

    days () {
      return this.hours / 24
    }
  },

  watch: {
    timer: {
      immediate: true,
      deep: true,
      handler ({ labels, UTC, timestamp }) {
        clearInterval(this.interval)

        this.$i18n.locale = labels.language
        this.timeLeft = timestamp - this.getTimestampWithUTCOffset(UTC)

        this.interval = setInterval(() => {
          if (!timestamp || !this.timeLeft || !this.timeLeft < 0) {
            clearInterval(this.interval)
          }
          this.timeLeft = timestamp - this.getTimestampWithUTCOffset(UTC)
        }, 1000)
      }
    }
  },

  methods: {
    getTimestampWithUTCOffset (UTCOffset) {
      let now = new Date()
      let currentTzOffset = -(now.getTimezoneOffset() / 60)
      let deltaTzOffset = UTCOffset - currentTzOffset
      let nowTimestamp = now.getTime()
      let deltaTzOffsetMilli = deltaTzOffset * 1000 * 60 * 60
      let dateWithUTCOffset = new Date(nowTimestamp + deltaTzOffsetMilli)
      return dateWithUTCOffset.getTime()
    },

    parse (value, remainder) {
      value = Math.floor(value)
      return (remainder) ? value % remainder : value
    }
  }
}
</script>

<style lang="sass" scoped>
@import '../../assets/sass/_colors.sass'
@import '../../assets/sass/_variables.sass'
@import '../../assets/sass/sections/element'

$main-font-size: 6rem

@mixin tabletFontSize ($property)
  .is-tablet &
    font-size: $property - 1.5
  @media (max-width: 800px)
    font-size: $property - 1.5

@mixin mobileFontSize ($property)
  .is-mobile &
    font-size: $property - 2.5
  @media (max-width: 400px)
    font-size: $property - 2.5

@mixin columnsFontSize ($index, $font_size)
  .b-columns#{$index} &
    font-size: $font_size - .5
    @include tabletFontSize($font_size - .5)
    @include mobileFontSize($font_size + 1.5)

// --- main
.b-timer
  color: #fff
  font-size: $main-font-size
  text-align: center
  padding: 0.8rem
  &.is-editable:hover
    cursor: pointer

  .is-mobile &,
  .is-tablet &
    width: 90%
  @media only screen and (max-width: 768px)
    &
      width: 90%
  @media only screen and (max-width: 768px) and (min-height: 700px)
    &
      width: 90%

  @include tabletFontSize($main-font-size)
  @include mobileFontSize($main-font-size)

  @include columnsFontSize(2, $main-font-size - 1.5)
  @include columnsFontSize(3, $main-font-size - 2)

.label
  font-size: .5em

.number
  min-width: 2.2em
  padding: 0.2em 0 0.2em 0.4em

  background: rgba(51, 51, 51, .5)

  font-size: 1em
  text-align: center

  text-shadow: 0px 2px 2px rgba(0, 0, 0, 0.25)
  letter-spacing: 0.4em
  border-radius: .2rem

  .is-mobile &,
  .is-tablet &
    min-width: none
    padding: 0.2em 0.2em
    letter-spacing: 0
  @media only screen and (max-width: 768px)
    &
      min-width:none
      padding: 0.2em 0.2em
      letter-spacing: 0

  position: relative

  &-divider
    width: .3em
    font-size: .7em
    &::before
      content: ':'
      position: relative
      top: -.1em

</style>
