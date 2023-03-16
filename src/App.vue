<template>
  <div>
    <div v-for="row in rows" class="row" >
      <div v-for="element in row" :key="element.key" class="max-width" >
        <span class="button" :class="'color-down-' + element.key, 'color-up-' + element.key"
          @mousedown="downPress(element.key)"
        > {{ element.text }}</span>
      </div>
    </div>
    <div class="counter">
      Counter: {{ timerCount  }}
    </div>
    <div class="repeat">
      <button @click="repeat()">Repeat</button>
    </div>
  </div>
</template>
<script>
export default {
  name: 'App',
  data() {
    return {
      timerCount: 60,
      rows: {
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
          }
        ]
      },
      presedKeys: []
    }
  },
  watch: {
    timerCount: {
      handler(value) {
        if (value > 0) {
          setTimeout(() => {
            this.timerCount--;
          }, 1000);
        } else {
          this.resetColor();
          this.timerCount = 60
        }
    },
    immediate: true // asigura ca watcherul se porneste la crearea componentului
    }
  },
  methods: {
    downPress(elementKey) {
      if (!this.presedKeys.includes(elementKey)) {
        this.presedKeys.push(elementKey);
      }

      this.setColorState("color-down-", elementKey, "blue");
      setTimeout(() => {
        this.setColorState("color-up-", elementKey, "green");
      }, 3000);
    },  
    setColorState(subClassName, elementKey, color) {
      const className = subClassName + elementKey;
      document.getElementsByClassName(className)[0].style.color = color;
    },
    resetColor() {
      this.presedKeys.forEach(key => {
        this.setColorState("color-down-", key, "gray");
        this.setColorState("color-up-", key, "gray");
      });
    },
    repeat() {
      let counter = 1;

      this.presedKeys.forEach(key => {
        setTimeout(() => {
          this.setColorState("color-up-", key, "green");
        }, counter * 200);
        counter++;
      });
    }
  }
}
</script>
<style>
body {
  transform: scale(1.8);
  transform-origin: 0 0;
}

.counter {
  margin-top: 20px;
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
