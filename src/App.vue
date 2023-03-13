<template>
  <div>
    <div>
      <div class="row">
        <div v-for="element in row1" :key="element" class="max-width">
          <span class="button" @click="clickButton(element)">{{ element }}</span>
        </div>
      </div>

      <div class="row">
        <div v-for="element in row2" :key="element" class="max-width">
          <span class="button" @click="clickButton(element)">{{ element }}</span>
        </div>
      </div>
      
      <div class="row">
        <div v-for="element in row3" :key="element" class="max-width">
          <span class="button" @click="clickButton(element)">{{ element }}</span>
        </div>
      </div>
      
      <div class="row">
        <div v-for="element in row4" :key="element" class="max-width">
          <span class="button" @click="clickButton(element)">{{ element }}</span>
        </div>
      </div>
      
      <div class="row">
        <div v-for="element in row5" :key="element" class="max-width">
          <span class="button" @click="clickButton(element)">{{ element }}</span>
        </div>
      </div>
    </div>
  </div>
</template>
<script>
export default {
  name: 'App',
  data() {
    return {
      row1: ["`", "1", "2", "3", "4", "5", "6", "7", "8", "9", "0", "-", "=", "backspace"],
      row2: ["TAB", "Q", "W", "E", "R", "T", "Y", "U", "I", "O", "P", "[", "]", "\\"],
      row3: ["Caps Lock", "A", "S", "D", "F", "G", "H", "J", "K", "L", ";", "'", "Enter"],
      row4: ["Shift", "Z", "X", "C", "V", "B", "N", "M", ",", ".", "/", "Shift"],
      row5: ["Ctrl", "FN", "Windows", "Alt", "Space", "Alt", "Ctrl"],
    }
  },
  methods: {
    clickButton(element) {
      console.log(element)
    }
  }
}
</script>
<style>

.button {
  cursor: pointer;
  margin-left: 10px;
  height: 20px;
  padding: 5px;
  background-color: gray;
  border-radius: 2px;
  border: 2px solid black;
}

.max-width {
  display: inline;
}

.row {
  margin-top: 15px;
}
</style>
