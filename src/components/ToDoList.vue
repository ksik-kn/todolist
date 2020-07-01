<template>
  <div>
    <div>To Do List</div>
    <table>
      <tr v-for="item in items" :key="item.name">
        <th>{{ item.taskname }}</th>
        <th>{{ item.deadline }}</th>
        <th v-if="item.state == 0">未完了</th>
        <th v-else>完了済み</th>
        <th>
          <button v-if="item.state == 0" @click="finished(item)">完了</button>
          <button v-else @click="finished(item)">完了解除</button>
        </th>
        <th>
          <button @click="remove(item)">削除</button>
        </th>
      </tr>
    </table>
    <div>
      <label>
        タスク
        <input type="text" v-model="newTaskName" />
      </label>
      <label>
        締め切り
        <input type="text" v-model="newDeadline" />
      </label>
      <button @click="addItem">追加</button>
    </div>
  </div>
</template>

<script>
export default {
  name: "ToDoList",
  data() {
    return {
      items: [
        { taskname: "タスク1", deadline: "2020/6/30", state: 1 },
        { taskname: "タスク2", deadline: "2000/7/1", state: 0 }
      ],
      newTaskName: "",
      newDeadline: ""
    };
  },
  methods: {
    addItem() {
      if (this.newTaskName != "") {
        this.items.push({
          taskname: this.newTaskName,
          deadline: this.newDeadline,
          state: 0
        });
        this.newTaskName = "";
        this.newDeadline = "";
      }
    },
    finished: function(item) {
      item.state = item.state ? 0 : 1;
    },
    remove: function(item) {
      var items = this.items;
      var index = items.indexOf(item);
      items.splice(index, 1);
    }
  }
};
</script>

<style></style>