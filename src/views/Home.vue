<template>
  <div class="home">
    <h1>Simple Text editor in Vue</h1>
    <div class="container">
      <div class="commands">
        <el-button type="primary" @click="modifyText('bold')">
          Bold
        </el-button>
        <el-button type="primary" @click="modifyText('italic')">
          Italic
        </el-button>
        <el-button type="primary" @click="modifyText('underline')">
          Underline
        </el-button>
        <el-button type="primary" @click="modifyText('strikeThrough')">
          Strike
        </el-button>
      </div>
      <div class="text-editor" contenteditable="true">Type anything here</div>
    </div>
    <div class="generated-html"></div>
  </div>
</template>
<script>
export default {
  data() {
    return {}
  },
  methods: {
    modifyText(val) {
      document.execCommand(val, false, '')
    }
  }
}
</script>
<style lang="scss" scoped>
.home {
  width: 100vw;
  display: flex;
  justify-content: center;
  flex-flow: column;
  align-items: center;
}
.container {
  display: flex;
}
.commands {
  width: 150px;
  padding: 20px;
  .el-button {
    width: 130px;
    margin: 10px;
  }
}
.text-editor {
  width: 60vw;
  height: 400px;
  margin-top: 10px;
  box-shadow: 1px 1px 10px #ccc;
  border-radius: 4px;
  padding: 20px;
  font-size: 20px;
  &:focus {
    border: 0;
    outline: 0;
  }
  &:active {
    border: 0;
    outline: 0;
  }
}
</style>
