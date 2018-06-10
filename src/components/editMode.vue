<template>
  <div class="list">
    <div class="edit-area">
      <div class="header">
        <div class="line">
          <div class="title">
            <input type="text" placeholder="Type the title">
          </div>
          <div class="remark">
            <i class="far fa-star"></i>
            <!-- <i class="fas fa-star"></i> -->
          </div>
          <div class="edit">
            <i class="fas fa-pencil-alt"></i>
          </div>
        </div>
      </div> <!-- header -->
      <div class="form-g">
        <div class="title">
          <i class="far fa-calendar-alt"></i><span>Deadline</span>
        </div>
        <input type="date">
      </div>
      <div class="form-g">
        <div class="title">
          <i class="far fa-file"></i><span>File</span>
        </div>
        <input type="file" name="file-btn">
        <label for="file-btn">
          <i class="fas fa-plus"></i>
        </label>
      </div>
      <div class="form-g">
        <div class="title">
          <i class="far fa-comment-dots"></i><span>Comment</span>
        </div>
        <textarea></textarea>
      </div>
      <div class="btns">
        <button class="btn n">
          <i class="fas fa-times"></i>Cancel
        </button>
        <button class="btn y">
          <i class="fas fa-plus"></i>Add Task
        </button>
      </div>
    </div><!-- edit-area -->

  </div>  <!-- list -->
</template>

<style lang="sass" scoped>
  @import "./src/sass/global.sass"
  .edit-area
    margin-top: 9px
    margin-bottom: 16px
    .edit
      color: $blue
    .form-g
      padding-left: 72px
      margin-top: 24px
      .title
        margin-bottom: 7px
        span
          font-size: $font-m
          margin-left: 10px

    textarea
      width: 445px
      height: 120px

    input:first-of-type, textarea
      margin-left: 23px

    input, textarea
      border: none
      outline: none

    input[type="text"], input[type="date"]
      height: 35px
      padding-left: 10px

    input[type="text"]
      width: 80%

    input[type="file"]
      width: 0px
      height: 0px
      opacity: 0

      + label
        display: inline-block
        padding: 8px 10px
        background-color: $gray
        border-radius: 2px
        color: #fff

    .btns
      display: flex
      margin-top: 24px
      button
        width: 50%
        border: 0
        outline: 0
        font-size: $font-l
        padding: 16px 0
        cursor: pointer
        i
          margin-right: 15px

        &.n
          background-color: #fff
          color: #d0021b
        &.y
          background-color: $blue
          color: #fff
</style>