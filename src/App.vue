<template>
  <div id="app">
     <h1>在线翻译</h1>
     <h5 class="text-success">简单易用便捷</h5>
     <translateForm v-on:survey="translateText"></translateForm>
     <translateOutput v-text='translatedText'></translateOutput>
  </div>
</template>


<script>
import translateForm from './components/TranslateForm.vue'
import translateOutput from './components/TranslateOutput.vue'

export default {
  name: 'App',
  data:function(){
    return{
      translatedText:'',
    }
  },
  components:{
    translateForm,
    translateOutput
  },
  methods:{
    translateText:function(text,language){
      // alert(text);
      this.$http.get('https://translate.yandex.net/api/v1.5/tr.json/translate?key=trnsl.1.1.20180308T074753Z.19c10f31250d5179.83f4a2dd71380a757af506c049cb6b152d1c852c&lang='+language+'&text='+text)
      .then((response)=>{
          // console.log(response.body.text[0]);
          this.translatedText=response.body.text[0];
      })
    }
  }
}
</script>

<style>
#app {
  margin-left: -60px;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 30px;
}
</style>
