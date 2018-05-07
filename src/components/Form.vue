<template>
  <div>Formページ
  <headComp></headComp>
  <TextareaComp></TextareaComp>
  <StringComp></StringComp>
  <button v-on:click="buttonAction">{{button}}</button>
  </div>
</template>

<script>
import HeadComp from './modules/HeadComp'
import TextareaComp from './modules/TextareaComp'
import StringComp from './modules/StringComp'
/** vuex */
import { mapActions, mapGetters } from 'vuex'

export default {
  name: 'form',
  components: { HeadComp, TextareaComp, StringComp },
  data () {
    return {
      msg: 'Welcome to Your Vue.js App'
    }
  },

  /*
   * storeのformモジュールについて、
   * viewのmethodとstoreのactionをバインドしている
   */
  methods: mapActions('Form', {
    'buttonAction': 'buttonAction'
  }),
  /** 再度レンダリング */
  computed: mapGetters('Form', {
    'button': 'getButton'
  })
}
</script>
