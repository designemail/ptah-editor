<script>
import * as types from '@editor/types'
import * as _ from 'lodash-es'
import Seeder from '@editor/seeder'
import defaults from '../../mixins/defaults'
import sectionMedia from '../../mixins/sectionMedia'

const GROUP_NAME = 'Products'
const NAME = 'ProductsAshOfGods01'
const BG_SECTION = 'none'
const COVER = 'https://cdn.ptah.pro/tst/5ef9a42509b4c100015ca9d4/f85f61c9-b2e6-472e-a37a-5182a64f8a98.jpg'
const DESCRIPTION = 'Product list side expanded view'

let prev = [
  'https://cdn.ptah.pro/tst/5ef9a42509b4c100015ca9d4/17be8b91-bd31-4e34-b750-5805c1aa31a7.png',
  'https://cdn.ptah.pro/tst/5ef9a42509b4c100015ca9d4/14ba8d42-d901-44c5-99cd-7b39f0e1ba29.png',
  'https://cdn.ptah.pro/tst/5ef9a42509b4c100015ca9d4/4f82d5c0-e7a3-46f4-81ac-e1469b4792fb.png',
  'https://cdn.ptah.pro/tst/5ef9a42509b4c100015ca9d4/2478c9a1-eb5e-40bd-8558-c2d5bbfca033.png'
]

let label = [
  'Start', 'Full', 'Delux', 'Ultimate'
]

let price = [
  '9.99', '19.99', '29.99', '39.99'
]

const [
  C_CUSTOM_1,
  C_CUSTOM_2,
  C_CUSTOM_3,
  C_CUSTOM_4
] = Array.from(new Array(4), (x, i) => {
  return [
    {
      element: {
        styles: {
          'background-image': `url(${prev[i]})`,
          'background-color': 'rgba(0, 0, 0, 0)',
          'background-repeat': 'no-repeat',
          'background-size': 'contain',
          'width': '190px',
          'height': '190px'
        },
        media: {
          'is-mobile': {
            'width': '190px',
            'height': '190px'
          }
        }
      }
    },
    {
      element: {
        text: `<h3>${label[i]} edition</h3>`,
        styles: {
          'font-size': '2.4rem',
          'color': '#ECD19A',
          'padding-bottom': '30px'
        },
        media: {
          'is-mobile': {
            'font-size': '2.4rem',
            'color': '#ECD19A',
            'padding-bottom': '30px'
          }
        }
      }
    },
    {
      element: {
        text: `$${price[i]}`,
        styles: {
          'background-color': '#A1210E',
          'color': '#ECD19A',
          'font-size': '2.4rem',
          'text-align': 'center',
          'width': '214px',
          'height': '54px',
          'border-width': '1px',
          'border-style': 'solid',
          'border-color': '#ECD19A',
          'margin-bottom': '20px'
        },
        pseudo: {
          hover: {
            'color': '#fff',
            'background-color': '#A1210E !important'
          }
        },
        media: {
          'is-mobile': {
            'font-size': '2rem',
            'width': '191px',
            'height': '46px',
            'margin-bottom': '20px'
          }
        }
      }
    }
  ]
})

const [
  C_CUSTOM_1_M,
  C_CUSTOM_2_M,
  C_CUSTOM_3_M,
  C_CUSTOM_4_M
] = Array.from(new Array(4), (x, i) => {
  return [
    {
      element: {
        styles: {
          'background-image': `url(${prev[i]})`,
          'background-color': 'rgba(0, 0, 0, 0)',
          'background-repeat': 'no-repeat',
          'background-size': 'contain',
          'width': '190px',
          'height': '190px'
        }
      }
    },
    {
      element: {
        text: `<h3>${label[i]} Edition</h3>`,
        styles: {
          'font-size': '2.4rem',
          'color': '#ECD19A'
        },
        media: {
          'is-mobile': {
            'font-size': '2.4rem'
          }
        }
      }
    }
  ]
})

const C_CUSTOM_1D = [
  {
    element: {
      colorFill: {
        color: '#ECD19A'
      },
      icon: {
        value: 'checkMark',
        name: 'checkMark',
        text: '<strong>Digital game copy</strong>'
      },
      styles: {
        color: '#ECD19A'
      }
    }
  },
  {
    element: {
      colorFill: {
        color: 'rgba(0,0,0,0)'
      },
      icon: {
        value: 'checkMark',
        name: 'checkMark',
        text: '<strong>Horse</strong>'
      },
      styles: {
        color: '#ffffff'
      }
    }
  },
  {
    element: {
      colorFill: {
        color: 'rgba(0,0,0,0)'
      },
      icon: {
        value: 'checkMark',
        name: 'checkMark',
        text: '<strong>Great sword</strong>'
      },
      styles: {
        color: '#ffffff'
      }
    }
  },
  {
    element: {
      colorFill: {
        color: 'rgba(0,0,0,0)'
      },
      icon: {
        value: 'checkMark',
        name: 'checkMark',
        text: '<strong>Digital soundtrack</strong>'
      },
      styles: {
        color: '#ffffff'
      }
    }
  }
]

const C_CUSTOM_2D = [
  {
    element: {
      colorFill: {
        color: '#ECD19A'
      },
      icon: {
        value: 'checkMark',
        name: 'checkMark',
        text: '<strong>Digital game copy</strong>'
      },
      styles: {
        color: '#ffffff'
      }
    }
  },
  {
    element: {
      colorFill: {
        color: '#ECD19A'
      },
      icon: {
        value: 'checkMark',
        name: 'checkMark',
        text: '<strong>Horse</strong>'
      },
      styles: {
        color: '#ffffff'
      }
    }
  },
  {
    element: {
      colorFill: {
        color: 'rgba(0,0,0,0)'
      },
      icon: {
        value: 'checkMark',
        name: 'checkMark',
        text: '<strong>Great sword</strong>'
      },
      styles: {
        color: '#ffffff'
      }
    }
  },
  {
    element: {
      colorFill: {
        color: 'rgba(0,0,0,0)'
      },
      icon: {
        value: 'checkMark',
        name: 'checkMark',
        text: '<strong>Digital soundtrack</strong>'
      },
      styles: {
        color: '#ffffff'
      }
    }
  }
]

const C_CUSTOM_3D = [
  {
    element: {
      colorFill: {
        color: '#ECD19A'
      },
      icon: {
        value: 'checkMark',
        name: 'checkMark',
        text: '<strong>Digital game copy</strong>'
      },
      styles: {
        color: '#ffffff'
      }
    }
  },
  {
    element: {
      colorFill: {
        color: '#ECD19A'
      },
      icon: {
        value: 'checkMark',
        name: 'checkMark',
        text: '<strong>Horse</strong>'
      },
      styles: {
        color: '#ffffff'
      }
    }
  },
  {
    element: {
      colorFill: {
        color: '#ECD19A'
      },
      icon: {
        value: 'checkMark',
        name: 'checkMark',
        text: '<strong>Great sword</strong>'
      },
      styles: {
        color: '#ffffff'
      }
    }
  },
  {
    element: {
      colorFill: {
        color: 'rgba(0,0,0,0)'
      },
      icon: {
        value: 'checkMark',
        name: 'checkMark',
        text: '<strong>Digital soundtrack</strong>'
      },
      styles: {
        color: '#ffffff'
      }
    }
  }
]

const C_CUSTOM_4D = [
  {
    element: {
      colorFill: {
        color: '#ECD19A'
      },
      icon: {
        value: 'checkMark',
        name: 'checkMark',
        text: '<strong>Digital game copy</strong>'
      },
      styles: {
        color: '#ffffff'
      }
    }
  },
  {
    element: {
      colorFill: {
        color: '#ECD19A'
      },
      icon: {
        value: 'checkMark',
        name: 'checkMark',
        text: '<strong>Horse</strong>'
      },
      styles: {
        color: '#ffffff'
      }
    }
  },
  {
    element: {
      colorFill: {
        color: '#ECD19A'
      },
      icon: {
        value: 'checkMark',
        name: 'checkMark',
        text: '<strong>Great sword</strong>'
      },
      styles: {
        color: '#ffffff'
      }
    }
  },
  {
    element: {
      colorFill: {
        color: '#ECD19A'
      },
      icon: {
        value: 'checkMark',
        name: 'checkMark',
        text: '<strong>Digital soundtrack</strong>'
      },
      styles: {
        color: '#ffffff'
      }
    }
  }
]

const C_CUSTOM_CONTAINER = {
  styles: {
    'flex-direction': 'column',
    'align-items': 'center'
  }
}

const C_CUSTOM_CONTAINER_M = {
  styles: {
    'flex-direction': 'column',
    'align-items': 'center'
  }
}

const C_CUSTOM_CONTAINER_D = {
  styles: {
    'flex-direction': 'column',
    'align-items': 'flex-start',
    'padding-top': '10px',
    'padding-left': '85px'
  },
  media: {
    'is-mobile': {
      'padding-top': '10px',
      'padding-left': '80px'
    }
  }
}

const SCHEMA_CUSTOM = {
  mainStyle: {
    styles: {
      'background-image': BG_SECTION,
      'background-color': '#000000',
      'padding-top': '80px',
      'padding-bottom': '80px'
    },
    media: {
      'is-mobile': {
        'padding-top': '0px',
        'padding-bottom': '40px'
      }
    },
    overlay: {
      color: 'rgba(0,0,0,1)',
      opacity: '0'
    }
  },
  containerStandart: _.merge({}, C_CUSTOM_CONTAINER),
  containerStandartM: _.merge({}, C_CUSTOM_CONTAINER_M),
  containerStandartD: _.merge({}, C_CUSTOM_CONTAINER_D),
  containerFull: _.merge({}, C_CUSTOM_CONTAINER),
  containerFullM: _.merge({}, C_CUSTOM_CONTAINER_M),
  containerFullD: _.merge({}, C_CUSTOM_CONTAINER_D),
  containerDeluxe: _.merge({}, C_CUSTOM_CONTAINER),
  containerDeluxeM: _.merge({}, C_CUSTOM_CONTAINER_M),
  containerDeluxeD: _.merge({}, C_CUSTOM_CONTAINER_D),
  containerUltimate: _.merge({}, C_CUSTOM_CONTAINER),
  containerUltimateM: _.merge({}, C_CUSTOM_CONTAINER_M),
  containerUltimateD: _.merge({}, C_CUSTOM_CONTAINER_D),
  componentsStandart: _.merge({}, C_CUSTOM_1),
  componentsStandartM: _.merge({}, C_CUSTOM_1_M),
  componentsStandartD: _.merge({}, C_CUSTOM_1D),
  componentsFull: _.merge({}, C_CUSTOM_2),
  componentsFullM: _.merge({}, C_CUSTOM_2_M),
  componentsFullD: _.merge({}, C_CUSTOM_2D),
  componentsDeluxe: _.merge({}, C_CUSTOM_3),
  componentsDeluxeM: _.merge({}, C_CUSTOM_3_M),
  componentsDeluxeD: _.merge({}, C_CUSTOM_3D),
  componentsUltimate: _.merge({}, C_CUSTOM_4),
  componentsUltimateM: _.merge({}, C_CUSTOM_4_M),
  componentsUltimateD: _.merge({}, C_CUSTOM_4D),
  edited: true
}

const COMPONENTS = [
  {
    name: 'Pic',
    element: types.Image,
    type: 'image',
    class: 'b-image',
    label: 'Pic'
  },
  {
    name: 'TextElement',
    element: types.Text,
    type: 'text',
    class: 'b-text',
    label: 'text'
  },
  {
    name: 'Button',
    element: types.Button,
    type: 'button',
    class: 'b-button-test',
    label: 'button'
  }
]

const COMPONENTS_M = [
  {
    name: 'Pic',
    element: types.Image,
    type: 'image',
    class: 'b-image',
    label: 'Pic'
  },
  {
    name: 'TextElement',
    element: types.Text,
    type: 'text',
    class: 'b-text',
    label: 'text'
  }
]

const COMPONENTS_D = [
  {
    name: 'IconWithText',
    element: types.IconWithText,
    type: 'iconWithText',
    class: 'b-text-icon',
    label: 'icon with text'
  },
  {
    name: 'IconWithText',
    element: types.IconWithText,
    type: 'iconWithText',
    class: 'b-text-icon',
    label: 'icon with text'
  },
  {
    name: 'IconWithText',
    element: types.IconWithText,
    type: 'iconWithText',
    class: 'b-text-icon',
    label: 'icon with text'
  },
  {
    name: 'IconWithText',
    element: types.IconWithText,
    type: 'iconWithText',
    class: 'b-text-icon',
    label: 'icon with text'
  }
]

export default {
  name: NAME,

  group: GROUP_NAME,

  description: DESCRIPTION,

  mixins: [defaults, sectionMedia],

  cover: COVER,

  $schema: {
    mainStyle: types.ProductSection,
    container: types.StyleObject,
    containerStandart: types.StyleObject,
    containerStandartM: types.StyleObject,
    containerStandartD: types.StyleObject,
    containerFull: types.StyleObject,
    containerFullM: types.StyleObject,
    containerFullD: types.StyleObject,
    containerDeluxe: types.StyleObject,
    containerDeluxeM: types.StyleObject,
    containerDeluxeD: types.StyleObject,
    containerUltimate: types.StyleObject,
    containerUltimateM: types.StyleObject,
    containerUltimateD: types.StyleObject,
    componentsStandart: _.merge([], COMPONENTS),
    componentsStandartM: _.merge([], COMPONENTS_M),
    componentsStandartD: _.merge([], COMPONENTS_D),
    componentsFull: _.merge([], COMPONENTS),
    componentsFullM: _.merge([], COMPONENTS_M),
    componentsFullD: _.merge([], COMPONENTS_D),
    componentsDeluxe: _.merge([], COMPONENTS),
    componentsDeluxeM: _.merge([], COMPONENTS_M),
    componentsDeluxeD: _.merge([], COMPONENTS_D),
    componentsUltimate: _.merge([], COMPONENTS),
    componentsUltimateM: _.merge([], COMPONENTS_M),
    componentsUltimateD: _.merge([], COMPONENTS_D),
    heightRightStage: 0
  },

  methods: {
    selectProduct (key) {
      this.$sectionData.mainStyle.selectProduct.name = key
    },

    calcHeightRightStage () {
      let height = 0
      let slotsHeight = 0
      let index = this.$section.id
      let section = document.getElementById(`section_${index}`)

      let rightStage = section.querySelector('.b-products-columns-extend__right')
      let allItems = rightStage.querySelectorAll('.b-products-columns-extend__right-item')

      allItems.forEach(function (item, i, arr) {
        if (item.classList.contains('_hide')) return

        item.querySelectorAll('.b-slot').forEach(function (slot, i, arr) {
          slotsHeight += slot.offsetHeight
        })

        if (slotsHeight > height) height = slotsHeight
        slotsHeight = 0
      })

      this.$sectionData.heightRightStage = height
    }
  },

  created () {
    if (this.$sectionData.edited === undefined) {
      Seeder.seed(_.merge(this.$sectionData, SCHEMA_CUSTOM))
    }
  },

  mounted () {
    this.calcHeightRightStage()
  },

  updated () {
    this.calcHeightRightStage()
  }
}
</script>

<template>
  <section
    class="b-products-columns-extend"
    :class="$sectionData.mainStyle.classes"
    :style="[$sectionData.mainStyle.styles, $sectionData.objVarsMedia]"
    v-styler:section="$sectionData.mainStyle"
  >
    <slot name="menu"/>
    <slot name="video"/>
    <slot name="overlay"/>

    <div class="b-grid">
      <div class="b-section-padd">

        <div class="b-section-padd-border">
          <div class="b-grid__row b-products-columns-extend__row"
           :style="{
             'align-items' : $sectionData.mainStyle.styles['align-items'],
             '--color-active': $sectionData.mainStyle.itemHoverColor
             }">
            <div class="b-grid__col-8 b-grid__col-m-12 b-products-columns-extend__left hidden-m">
              <!-- b-products-columns-extend__left -->
              <div class="b-grid__row b-products-columns-extend__row">
                <div class="b-grid__col-6 b-products-columns-extend__left-item"
                 v-for="(product, key) in $sectionData.mainStyle.products"
                 :key="key"
                 v-if="$sectionData.mainStyle.products[key].visible"
                 :data-index="key"
                 product-extend-preview="b-products-columns-extend__right-item_active"
                 @click="selectProduct(key)"
                 :class="{ 'b-products-columns-extend__left-item_active': $sectionData.mainStyle.selectProduct.name === key }"
                >
                  <sandbox
                    class="b-sandbox"
                    :container-path="`$sectionData.container${key}M`"
                    :components-path="`$sectionData.components${key}M`"
                  >

                    <draggable v-model="$sectionData['components' + key]" class="b-draggable-slot" :style="$sectionData[`container${key}M`].styles" @start="$_drag(`components${key}M`)" @change="$_dragStop">
                      <div
                        v-for="(component, index) in $sectionData[`components${key}M`]"
                        v-if="$sectionData[`components${key}M`].length !== 0"
                        :key="index"
                      >
                        <component class="b-products-columns-component"
                         v-styler:for="{ el: $sectionData[`components${key}M`][index].element, path: `$sectionData.components${key}M[${index}].element`, type: $sectionData[`components${key}M`][index].type, label: $sectionData[`components${key}M`][index].label }"
                         :is="component.name"
                         :href="$sectionData[`components${key}M`][index].element.link.href"
                         :target="$sectionData[`components${key}M`][index].element.link.target"
                         :path="`components${key}M[${index}].element`"
                         :style="$sectionData[`components${key}M`][index].element.styles"
                         :class="[$sectionData[`components${key}M`][index].element.classes, $sectionData[`components${key}M`][index].class]"
                        >
                          <div v-html="$sectionData[`components${key}M`][index].element.text"></div>
                        </component>
                      </div>
                    </draggable>
                  </sandbox>
                </div>
              </div><!--/.b-products-columns-extend__left-->
            </div>
            <div class="b-grid__col-4 b-grid__col-m-12 b-products-columns-extend__right"
                 :style="{ height: $sectionData.heightRightStage + 'px' }"
            >
              <!-- b-products-columns-extend__right -->
              <div class="b-products-columns-extend__right-stage">
                <div class="b-products-columns-extend__right-item"
                 v-for="(product, key) in $sectionData.mainStyle.products"
                 :key="key"
                 :class="[{ 'b-products-columns-extend__right-item_active': ($sectionData.mainStyle.selectProduct.name === key && $sectionData.mainStyle.products[key].visible)}, { '_hide' : !$sectionData.mainStyle.products[key].visible }]"
                 :product-extend-stage="key"
                 :data-index="key"
                >
                  <sandbox
                    class="b-sandbox"
                    :container-path="`$sectionData.container${key}`"
                    :components-path="`$sectionData.components${key}`"
                  >
                    <draggable v-model="$sectionData['components' + key]" class="b-draggable-slot" :style="$sectionData[`container${key}`].styles" @start="$_drag(`components${key}`)" @change="$_dragStop">
                      <div
                        v-for="(component, index) in $sectionData[`components${key}`]"
                        v-if="$sectionData[`components${key}`].length !== 0"
                        :key="index"
                      >
                        <component class="b-products-columns-component"
                         v-styler:for="{ el: $sectionData[`components${key}`][index].element, path: `$sectionData.components${key}[${index}].element`, type: $sectionData[`components${key}`][index].type, label: $sectionData[`components${key}`][index].label }"
                         :is="component.name"
                         :href="$sectionData[`components${key}`][index].element.link.href"
                         :target="$sectionData[`components${key}`][index].element.link.target"
                         :path="`components${key}[${index}].element`"
                         :style="$sectionData[`components${key}`][index].element.styles"
                         :class="[$sectionData[`components${key}`][index].element.classes, $sectionData[`components${key}`][index].class]"
                        >
                          <div v-html="$sectionData[`components${key}`][index].element.text"></div>
                        </component>
                      </div>
                    </draggable>
                  </sandbox>
                  <sandbox
                    class="b-sandbox"
                    :container-path="`$sectionData.container${key}D`"
                    :components-path="`$sectionData.components${key}D`"
                  >
                    <draggable v-model="$sectionData['components' + key + 'D']" class="b-draggable-slot" :style="$sectionData[`container${key}D`].styles" @start="$_drag(`components${key}D`)" @change="$_dragStop">
                      <div
                        v-for="(component, index) in $sectionData[`components${key}D`]"
                        v-if="$sectionData[`components${key}D`].length !== 0"
                        :key="index"
                      >
                        <component class="b-products-columns-component"
                         v-styler:for="{ el: $sectionData[`components${key}D`][index].element, path: `$sectionData.components${key}D[${index}].element`, type: $sectionData[`components${key}D`][index].type, label: $sectionData[`components${key}D`][index].label }"
                         :is="component.name"
                         :href="$sectionData[`components${key}D`][index].element.link.href"
                         :target="$sectionData[`components${key}D`][index].element.link.target"
                         :path="`components${key}D[${index}].element`"
                         :style="$sectionData[`components${key}D`][index].element.styles"
                         :class="[$sectionData[`components${key}D`][index].element.classes, $sectionData[`components${key}D`][index].class]"
                        >
                          <div v-html="$sectionData[`components${key}D`][index].element.text"></div>
                        </component>
                      </div>
                    </draggable>
                  </sandbox>
                </div>
              </div><!--/.b-products-columns-extend__right-->
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<style lang="sass" scoped>
</style>
