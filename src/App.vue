<template>
  <div>
    <div>
      <div class="row">
        <div v-for="element in row1" :key="element.key" class="max-width" >
          <span class="button" :class="'color-down-' + element.key, 'color-up-' + element.key"
            @mousedown="downPress(element.key)"
            @mouseup="upPress(element.key)"
          > {{ element.text }}</span>
        </div>
      </div>

      <div class="row">
        <div v-for="element in row2" :key="element.key" class="max-width" >
          <span class="button" :class="'color-down-' + element.key, 'color-up-' + element.key"
            @mousedown="downPress(element.key)"
            @mouseup="upPress(element.key)"
          > {{ element.text }}</span>
        </div>
      </div>
      
      <div class="row">
        <div v-for="element in row3" :key="element.key" class="max-width" >
          <span class="button" :class="'color-down-' + element.key, 'color-up-' + element.key"
            @mousedown="downPress(element.key)"
            @mouseup="upPress(element.key)"
          > {{ element.text }}</span>
        </div>
      </div>
      
      <div class="row">
        <div v-for="element in row4" :key="element.key" class="max-width" >
          <span class="button" :class="'color-down-' + element.key, 'color-up-' + element.key"
            @mousedown="downPress(element.key)"
            @mouseup="upPress(element.key)"
          > {{ element.text }}</span>
        </div>
      </div>
      
      <div class="row">
        <div v-for="element in row5" :key="element.key" class="max-width" >
          <span class="button" :class="'color-down-' + element.key, 'color-up-' + element.key"
            @mousedown="downPress(element.key)"
            @mouseup="upPress(element.key)"
          > {{ element.text }}</span>
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
      row1: [
        {
          key: 'tilde', 
          text: "`"
        },
        {
          key: 'one', 
          text: "1"
        },
        {
          key: 'two', 
          text: "2"
        },
        {
          key: 'three', 
          text: "3"
        },
        {
          key: 'four', 
          text: "4"
        },
        {
          key: 'five', 
          text: "5"
        },
        {
          key: 'six', 
          text: "6"
        },
        {
          key: 'seven', 
          text: "7"
        },
        {
          key: 'eight', 
          text: "8"
        },
        {
          key: 'nine', 
          text: "9"
        },
        {
          key: 'zero', 
          text: "0"
        },
        {
          key: 'line', 
          text: "-"
        },
        {
          key: 'equal', 
          text: "="
        },
        {
          key: 'backspace', 
          text: "backspace"
        },
      ],
      row2: [
        {
          key: 'tab', 
          text: "TAB"
        },
        {
          key: 'q', 
          text: "Q"
        },
        {
          key: 'w', 
          text: "W"
        },
        {
          key: 'e', 
          text: "E"
        },
        {
          key: 'r', 
          text: "R"
        },
        {
          key: 't', 
          text: "T"
        },
        {
          key: 'y', 
          text: "Y"
        },
        {
          key: 'u', 
          text: "U"
        },
        {
          key: 'i', 
          text: "I"
        },
        {
          key: 'o', 
          text: "O"
        },
        {
          key: 'p', 
          text: "P"
        },
        {
          key: 'open-bracket', 
          text: "["
        },
        {
          key: 'closed-bracket', 
          text: "]"
        },
        {
          key: 'back-slash', 
          text: "\\"
        },
      ],
      row3: [
        {
          key: 'caps-lock', 
          text: "Caps Lock"
        },
        {
          key: 'a', 
          text: "A"
        },
        {
          key: 's', 
          text: "S"
        },
        {
          key: 'd', 
          text: "D"
        },
        {
          key: 'f', 
          text: "F"
        },
        {
          key: 'g', 
          text: "G"
        },
        {
          key: 'h', 
          text: "H"
        },
        {
          key: 'j', 
          text: "J"
        },
        {
          key: 'k', 
          text: "K"
        },
        {
          key: 'l', 
          text: "L"
        },
        {
          key: 'semicolons', 
          text: ";"
        },
        {
          key: "apostrophe", 
          text: "'"
        },
        {
          key: 'enter', 
          text: "Enter"
        },
      ],
      row4: [
        {
          key: 'left-shift', 
          text: "Shift"
        },
        {
          key: 'z', 
          text: "Z"
        },
        {
          key: 'x', 
          text: "X"
        },
        {
          key: 'c', 
          text: "C"
        },
        {
          key: 'v', 
          text: "V"
        },
        {
          key: 'b', 
          text: "B"
        },
        {
          key: 'n', 
          text: "N"
        },
        {
          key: 'm', 
          text: "M"
        },
        {
          key: '', 
          text: ","
        },
        {
          key: 'dot', 
          text: "."
        },
        {
          key: 'forward-slash', 
          text: "/"
        },
        {
          key: 'right-shift', 
          text: "Shift"
        },
      ],
      row5: [
        {
          key: 'left-control', 
          text: "Ctrl"
        },
        {
          key: 'fn', 
          text: "Fn"
        },
        {
          key: 'windows', 
          text: "Windows"
        },
        {
          key: 'left-alt', 
          text: "Alt"
        },
        {
          key: 'space', 
          text: "Space"
        },
        {
          key: 'right-alt', 
          text: "Alt"
        },
        {
          key: 'right-control', 
          text: "Ctrl"
        },
      ],
    }
  },
  methods: {
    downPress(element) {
      const className = 'color-down-' + element;
      document.getElementsByClassName(className)[0].style.color = "blue";
    },  
    upPress(element) {
      const className = 'color-up-' + element;
      document.getElementsByClassName(className)[0].style.color = "green";
    }
  }
}
</script>
<style>
body {
  transform: scale(1.8);
  transform-origin: 0 0;
}
.button {
  cursor: pointer;
  margin-left: 10px;
  padding: 3px;
  background-color: black;
  color: gray;
  border-radius: 2px;
  border: 2px solid gray;
}

.max-width {
  display: inline;
}

.row {
  margin-top: 15px;
}
</style>
