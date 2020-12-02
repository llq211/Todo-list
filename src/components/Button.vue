<template>
  <div class="out_box">
    <input type="text" name="" v-model="name" @keyup.enter="submit" placeholder="请输入代办事情">
    <button class="click" @click="submit">提交</button> 
    <ul>
      <li v-for="(item,index) in list" :key="index">
        <div class="box_todolist">
          <span>{{index+1}}、</span>
          <span>{{item}}</span>
          <button class="Delete" @click="remove(index)"></button>
        </div>
      </li>
    </ul>
  </div>

  
</template>

<script>
export default{
  name: "Button",
  data(){
    return{
      name: "",
      list: []
    }
  },
  methods: {
    submit: function(){
      this.list.push(this.name);
      this.name="";
    },
    remove: function(index) {
      this.list.splice(index,1);
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->