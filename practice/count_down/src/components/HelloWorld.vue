<template>
  <div class="hello">
    <button class="btn btn-primary"  @click="start">{{msg}}</button>
    <br/>
    <hr/>
    <button class="btn btn-primary">当前时间：{{present | getLocalTime}}</button>
    <br/>
    <hr/>
    <button class="btn btn-primary">{{left}}</button>
    <router-link to="now"> hello</router-link>
  </div>
</template>

<script>
export default {
  name: 'HelloWorld',
  data () {
    return {
      msg: '开始倒计时',
      present:"",
      Spring:"2018-02-15 00:00",
      left:0
    }
  },
  mounted(){
    this.present=new Date();
  },
  filters:{
    getLocalTime(t){
      return t.toLocaleString()
    }
},
  methods:{
    start(){
      this.left=(new Date(this.Spring)).getTime()-this.present.getTime()
    }

  },

}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h1, h2 {
  font-weight: normal;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
