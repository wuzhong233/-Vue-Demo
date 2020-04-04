<template>
  <div class="row" id="translateForm">
    <div class="lala">
      <form class="well form-inline" v-on:submit="formSubmit">
        <input class="form-control" type="text" v-model="textToTranslate" placeholder="输入需要翻译的内容" />
        <select class="form-control" v-model="language">
          <option value="en">英语</option>
          <option value="ru">俄语</option>
          <option value="ko">朝鲜语</option>
          <option value="ja">日语</option>
          <option value="es">西班牙语</option>
          <option value="it">意大利语</option>
          <option value="de">德语</option>
          <option value="zh">中文</option>
        </select>
        <input class="btn btn-primary" type="submit" value="翻译" />
      </form>
    </div>
  </div>
</template>
<script>
export default {
  name: "translateForm",
  data: function() {
    return {
      textToTranslate: "",
      language: ""
    };
  },
  methods: {
    formSubmit: function(e) {
      // alert(this.textToTranslate);
      this.$emit("formSubmit", this.textToTranslate, this.language);
      e.preventDefault();
    }
  },
  created: function() {
    this.language = "en";
  }
};
</script>

<style scoped>
.lala {
  float: none;
  display: block;
  margin-left: auto;
  margin-right: auto;
}
</style>