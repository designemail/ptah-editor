<template>
  <div class="b-panel">
    <h6 class="b-panel__title">
      Toggle settings
    </h6>

    <IndicatorPlatform />

    <div class="b-panel__layout _top-9">
      <div class="layout _top-2 _pr-05">
        <base-scroll-container>
          <div class="layout-padding">
            <!-- Typography -->
            <div class="b-panel__control">
              <base-caption>
                Text style
              </base-caption>
              <control-typography :show-text-styles="false" />
              <control-align/>
            </div>

            <!-- Control settings-->
            <div class="b-panel__control" v-if="!isMobile">
              <control-toggle-element-settings/>
            </div>

            <!-- Control padding/margin-->
            <div class="b-panel__control">
              <control-box/>
            </div>
          </div>
        </base-scroll-container>
      </div>
    </div>
  </div>
</template>

<script>
import ControlToggleElementSettings from '../controls/TheControlToggleElementSettings'
import ControlTypography from '../controls/TheControlTypography'
import ControlAlign from '../controls/TheControlAlign'
import ControlBox from '../controls/TheControlBox'
import IndicatorPlatform from '../IndicatorPlatform'
import { mapState } from 'vuex'

export default {
  name: 'ThePanelToggleElement',

  components: {
    IndicatorPlatform,
    ControlToggleElementSettings,
    ControlBox,
    ControlTypography,
    ControlAlign
  },

  computed: {
    ...mapState('Sidebar', [
      'isMobile'
    ])
  }
}
</script>
