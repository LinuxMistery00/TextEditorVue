<template>
  <div class="TextEditor">
    <textarea v-model="fileContent" rows="10" cols="40"></textarea>
    <div>
      <button class="SaveFileBTN" @click="saveFile">Save File</button>
    </div>
  </div>
</template>

<style scoped>
.TextEditor {
  display: flex;
  flex-direction: column;
  align-items: center;
  margin-top: 8%;
}

.TextEditor textarea {
  margin-bottom: 10px;
  border: 0;
  border-radius: 1.5vh;
  background-color: #212223;
  color: #f1f2f3;
  height: 30vh;
}

.SaveFileBTN {
  border: 0;
  border-radius: 3vh;
  width: 30vh;
  height: 5vh;
  font-size: 5vh;
  background-color: rgba(39, 225, 122, 1);
  color: #f1f2f3;
}

.SaveFileBTN:hover {
  background-color: rgba(39, 200, 100, 1);
}

@media (max-width: 410px) {
.TextEditor textarea {
  margin-top: 10%;
  width: 35vh;
}
}
</style>

<script>
export default {
  data() {
    return {
      fileContent: 'Edit this text...',
    };
  },
  methods: {
    saveFile() {
      const blob = new Blob([this.fileContent], { type: 'text/plain' });
      const url = URL.createObjectURL(blob);
      const link = document.createElement('a');
      link.href = url;
      link.setAttribute('download', 'edited-file.txt');
      document.body.appendChild(link);
      link.click();
      document.body.removeChild(link);
    },
  },
};
</script>
