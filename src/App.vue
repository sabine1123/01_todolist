
<template>
  <div id="app">
      <v-header></v-header>
      <div class="container">
      <div class="add">
        <i class="fas fa-plus"></i> Add Task
      </div>
      <v-list></v-list>
      <v-edit></v-edit>
      <!-- <router-view/> -->
    </div>
  </div>
</template>

<script>
import header from './components/header.vue'
import list from './components/listMode.vue'
import edit from './components/editMode.vue'

export default {
  name: 'App',
  data () {
    return {
      message: '',
      // TodoList 的資料，另外因為有排序功能，所以在此不會使用 computed
      todos: [],
      // 當前編輯的內容
      currentEdit: {},
      // 是否展開新的 todo
      isNewTodo: false,
      // 判斷目前顯示的分頁
      currentTab: 'all'
    }
  },
  components: {
    'v-header': header,
    'v-list': list,
    'v-edit': edit
  },
  methods: {
    addTodo () {
      this.isNewTodo = true
      this.currentEdit = {}
    },
    getData () {
      // 每次新增內容都會取得資料，包含 Todos 及排序
      const vm = this
      const api = '../todo.json'
      const sortApi = 'http://localhost:5000/sort'
      let todos = []
      vm.todos = []
      // 取得 Todos
      vm.$http.get(api).then((response) => {
        todos = response.data
        console.log(todos)
        // 取得 排序
        // return vm.$http.get(sortApi)
      // })
      // .then((response) => {
      //   const sortData = response.data.sort
      //   // 有排序資料時，則開始整理排序
      //   if (sortData) {
      //     // 整理出有對應 ID 的物件
      //     sortData.forEach((sortId, sortIndex) => {
      //       const todo = todos.find((item) => item.id === sortId)
      //       vm.todos.push(todo)
      //     })
      //     todos.forEach((todo) => {
      //       // 沒有排序 id 的內容，依然要存回 todos 內
      //       const hasSort = sortData.some((sortId) => todo.id === sortId)
      //       if (!hasSort) {
      //         vm.todos.push(todo)
      //       }
      //     })
      //   } else {
      //     vm.todos = todos
      //   }
      })
    },
    editTodo (id) {
      // 編輯 Todo，並把目前的 Todo 資訊傳入
      const vm = this
      this.isNewTodo = false
      vm.currentEdit = vm.todos.find((item) => item.id === id)
    },
    closeEdit () {}
      // 關閉 編輯
  }
}
</script>

<style lang="sass">
@import "./src/sass/global.sass"
ul
  margin: 0
  padding: 0
  li
    list-style: none

body
  background-color: #e1e1e1
  font-family: 'Roboto', sans-serif

.container
  width: 620px
  margin: 0 auto

  .add
    font-size: $font-l
    color: $gray
    background-color: #fff
    border-radius: 5px
    border: 2px solid $gray
    padding: 18px 0 18px 32px
    margin-top: 24px
    cursor: pointer
</style>

