<template>
  <div id="translateForm">
    <div class="">
      <form class="form-group" v-on:submit="formSubmit">
        <input type="text" v-model="text" placeholder="需要翻译的内容">
      <select v-model="language">
        <option value="en">English</option>
        <option value="ru">Russion</option>
        <option value="ko">Korean</option>
        <option value="ja">Janpenese</option>

      </select>
      <input class="btn btn-success btn-width" type="submit" value="翻译">
    </form>
   </div>

  </div>
</template>

<script>
export default {
  name: 'translateForm',
  data:function(){
   return{
    text:'',
    language:''
   }
  },
  methods:{
    formSubmit:function(e){
      // alert(this.text);
      this.$emit("survey",this.text,this.language);
      e.preventDefault();
    }
  }
}
</script>

<style>
#translateForm {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
.btn-width{
  height: 30px;
  padding: 1px 14px;
}
</style>
