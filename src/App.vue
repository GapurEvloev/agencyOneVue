<template lang="pug">
  .wrapper
    header
      .navbar
        .container
          .navbar-content
            router-link.header-logo(
              to="/"
            ) AgencyOne
            .button-burger(
              @click="menuShow = !menuShow"
              :class="{ active: nemuShow }"
            )
              span.line.line-1
              span.line.line-2
              span.line.line-3
            .navbar-list__wrapper(
              :class="{ active: nemuShow }"
            )
              ul.navbar-list
                li.navbar-item(
                  v-for="link in linkMenu"
                  :key="link.title"
                )
                  router-link.navbar-link(
                    :to="`${link.url}`"
                  ) {{ link.title }}
</template>

<script>
export default {
  data () {
    return {
      menuShow: false,
      linkMenu: [
        {title: 'О компании', url: '/about'},
        {title: 'Избранное', url: '/selected-projects'},
        {title: 'Инструменты', url: '/instruments'}
      ]
    }
  }
}
</script>

<style lang="stylus">
#app
  padding 30px
  background-color #333
  color #fff
</style>
