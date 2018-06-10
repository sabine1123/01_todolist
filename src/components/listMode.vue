<template>
  <div class="list">
    <div class="header">
      <div class="line">
        <label class="checkbox-wrap">
          <input type="checkbox">
          <span class="checkmark"></span>
        </label>
        <div class="title">Type Something Here</div>
        <div class="remark">
          <i class="far fa-star"></i>
          <!-- <i class="fas fa-star"></i> -->
        </div>
        <div class="edit">
          <i class="fas fa-pencil-alt"></i>
        </div>
      </div>
    </div>
    <div class="icons">
      <div class="icon date">
        <i class="far fa-calendar-alt"></i>
        <span id="date">2018/06/05</span>
      </div>
      <div class="icon file">
        <i class="far fa-file"></i>
      </div>
      <div class="icon comment">
        <i class="far fa-comment-dots"></i>
      </div>
    </div>
  </div>
</template>

<style lang="sass">
  @import "./src/sass/global.sass"
  .list
    background-color: #f2f2f2
    margin-top: 8px
    .header
      border-radius: 5px
      padding: 24px 32px 0
      .line
        display: flex

        .title
          width: 436px
          font-size: $font-l
          margin: 0 0 15px 40px
          // overflow: hidden
          // white-space: nowrap
          // text-overflow: ellipsis
        .remark, .edit
          font-size: $font-l
          cursor: pointer
        .edit
          margin-left: 32px
    .icons
      display: flex
      color: #757575
      margin-left: 72px
      padding-bottom: 15px
      div
        margin-right: 16px
</style>