<template>
  <div id="app">
    <h1>在线翻译</h1>
    <h5 class="text-muted">简单/易用/便捷</h5>
    <translateForm v-on:formSubmit="translateText"></translateForm><br />
    <translateOutput v-text="translatedText"></translateOutput>
  </div>
</template>

<script>
import TranslateForm from "./components/TranslateForm.vue";
import TranslateOutput from "./components/TranslateOutput";

export default {
  name: "App",
  data: function() {
    return {
      translatedText: ""
    };
  },
  components: {
    TranslateForm,
    TranslateOutput
  },
  methods: {
    translateText: function(text, language) {
      // alert(text);
      this.$http
        .get(
          "https://translate.yandex.net/api/v1.5/tr.json/translate?key=trnsl.1.1.20180806T023828Z.262c5f4356ee8837.93b2f555c5f7937e029a263f958de5233b58c335&lang=" +
            language +
            "&text=" +
            text
        )
        .then(response => {
          //请求出来的数据有个返回值
          // console.log(response.body.text[0]);
          this.translatedText = response.body.text[0];
        });
    }
  }
};
</script>

<style scoped>
h1,
h5 {
  text-align: center;
  margin: 20px;
}
</style>
