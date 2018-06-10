<template>
    <header>
    <ul>
      <li class="active">My Tasks</li>
      <li>In Progress</li>
      <li>Completed</li>
    </ul>
  </header>
</template>

<style lang="sass" scoped>
header
  @import "./src/sass/global.sass"
  width: 100%
  background-color: #4A90E2
  ul
    display: flex
    justify-content: center
    li
      font-size: $font-l
      color: #00408B
      width: 220px
      text-align: center
      padding-top: 24px
      padding-bottom: 24px
      position: relative
      cursor: pointer
      &.active
        color: #fff
        &::after
          content: ''
          width: 160px
          height: 5px
          background-color: #00408B
          display: block
          position: absolute
          bottom: 0
          left: 30px
</style>