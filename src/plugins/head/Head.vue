<template>
<BlockComponent :data="data">
  <component :is="this.data.attrs.size" class="title" :class="sizeClass">
    {{getAttrValue('text') || '[No value]'}}
  </component>
</BlockComponent>
</template>

<script>
import BlockComponent from '@/components/BlockComponent.vue'
import attrMixin from '@/plugins/attrMixin'

export default {
  name: 'bj-head',
  mixins: [attrMixin],
  components: {
    BlockComponent,
  },
  inject: ['blockJS'],
  props: {
    data: Object,
  },
  computed: {
    sizeClass() {
      return `is-size-${this.data.attrs.size.substr(1)}`
    },
  },
}
</script>

<style lang="scss">
@import "~bulma/sass/utilities/_all";
</style>
