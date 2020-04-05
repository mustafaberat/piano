<template>
  <div @keydown="myPiano(event)" @keyup="pianoStyle(event)">
    <div class="piano-container">
      <div class="row">
        <div class="key-b" id="b-1" @click="playIt(0)">
          <audio></audio>
        </div>
        <div class="key-b" id="b-2" @click="playIt(1)">
          <audio></audio>
        </div>
        <div class="key-b" id="b-3" @click="playIt(2)">
          <audio></audio>
        </div>
        <div class="key-b" id="b-4" @click="playIt(3)">
          <audio></audio>
        </div>
        <div class="key-b" id="b-5" @click="playIt(4)">
          <audio></audio>
        </div>
        <div class="key-b" id="b-6" @click="playIt(5)">
          <audio></audio>
        </div>
        <div class="key-b" id="b-7" @click="playIt(6)">
          <audio></audio>
        </div>
        <div class="key-b" id="b-8" @click="playIt(7)">
          <audio></audio>
        </div>
        <div class="key-b" id="b-9" @click="playIt(8)">
          <audio></audio>
        </div>
        <div class="key-b" id="b-10" @click="playIt(9)">
          <audio></audio>
        </div>

        <div class="key-w" id="w-1" @click="playIt(10)">
          <audio></audio>
        </div>
        <div class="key-w" id="w-2" @click="playIt(11)">
          <audio></audio>
        </div>
        <div class="key-w" id="w-3" @click="playIt(12)">
          <audio></audio>
        </div>
        <div class="key-w" id="w-4" @click="playIt(13)">
          <audio></audio>
        </div>
        <div class="key-w" id="w-5" @click="playIt(14)">
          <audio></audio>
        </div>
        <div class="key-w" id="w-6" @click="playIt(15)">
          <audio></audio>
        </div>
        <div class="key-w" id="w-7" @click="playIt(16)">
          <audio></audio>
        </div>
        <div class="key-w" id="w-8" @click="playIt(17)">
          <audio></audio>
        </div>
        <div class="key-w" @click="playIt(18)"><audio></audio></div>
        <div class="key-w" @click="playIt(19)"><audio></audio></div>
        <div class="key-w" @click="playIt(20)"><audio></audio></div>
        <div class="key-w" @click="playIt(21)"><audio></audio></div>
        <div class="key-w" @click="playIt(22)"><audio></audio></div>
        <div class="key-w" @click="playIt(23)"><audio></audio></div>
        <div class="morediv">
          <a class="more" href="https://mustafaberat.now.sh/things">More..</a>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "Piano",
  data() {
    return {
      audioS: [
        "http://www.vibrationdata.com/piano_C_sharp.mp3",
        "http://www.freesound.org/data/previews/117/117712_646701-lq.mp3",
        "http://www.freesound.org/data/previews/117/117690_646701-lq.mp3",
        "http://www.freesound.org/data/previews/117/117692_646701-lq.mp3",
        "http://www.freesound.org/data/previews/117/117682_646701-lq.mp3",
        "http://www.freesound.org/data/previews/117/117685_646701-lq.mp3",
        "http://www.freesound.org/data/previews/117/117687_646701-lq.mp3",
        "http://www.vibrationdata.com/piano_F_sharp.mp3",
        "http://www.vibrationdata.com/piano_G_sharp.mp3",
        "http://www.vibrationdata.com/piano_A_sharp.mp3",
        "http://www.vibrationdata.com/piano_middle_C.mp3",
        "http://www.freesound.org/data/previews/117/117713_646701-lq.mp3",
        "http://www.freesound.org/data/previews/117/117689_646701-lq.mp3",
        "http://www.freesound.org/data/previews/117/117691_646701-lq.mp3",
        "http://www.freesound.org/data/previews/117/117693_646701-lq.mp3",
        "http://www.freesound.org/data/previews/117/117683_646701-lq.mp3",
        "http://www.freesound.org/data/previews/117/117684_646701-lq.mp3",
        "http://www.freesound.org/data/previews/117/117686_646701-lq.mp3",
        "http://www.freesound.org/data/previews/117/117688_646701-lq.mp3",
        "http://www.freesound.org/data/previews/117/117701_646701-lq.mp3",
        "http://www.tremblingsandwarblings.com/wp-content/uploads/2017/05/piano-Cs4-long.mp3",
        "http://mrclan.com/fastdl/tfc/sound/b3.wav",
        "http://www.dms489.com/Concepts_book/listings/Ch_14_Sound/instr_piano.wav",
        "http://www.tremblingsandwarblings.com/wp-content/uploads/2017/05/piano-Cs4-long.mp3",
        "http://ecee.colorado.edu/~mathys/ecen1200/hwcl09/c6.wav",
      ],
      //mouse click (play piano using mouse)
      audio: new Audio(),
      b1: document.getElementById("b-1"),
      b2: document.getElementById("b-2"),
      b3: document.getElementById("b-3"),
      b4: document.getElementById("b-4"),
      b5: document.getElementById("b-5"),
      b6: document.getElementById("b-6"),
      w1: document.getElementById("w-1"),
      w2: document.getElementById("w-2"),
      w3: document.getElementById("w-3"),
      w4: document.getElementById("w-4"),
      w5: document.getElementById("w-5"),
      w6: document.getElementById("w-6"),
      w7: document.getElementById("w-7"),
      w8: document.getElementById("w-8"),
    };
  }, //END OF DATA

  // METHODS
  methods: {
    playIt(n) {
      this.audio.src = this.audioS[n];
      this.audio.play();
    },

    myPiano(event) {
      var x = event.keyCode;
      switch (x) {
        case 87:
          this.audio.src = this.audioS[0];
          this.audio.play();
          this.b1.style["border-bottom-width"] = "1px";
          this.b1.style["height"] = "57%";
          break;
        case 69:
          this.audio.src = this.audioS[1];
          this.audio.play();
          this.b2.style["border-bottom-width"] = "1px";
          this.b2.style["height"] = "57%";
          break;
        case 84:
          this.audio.src = this.audioS[2];
          this.audio.play();
          this.b3.style["border-bottom-width"] = "1px";
          this.b3.style["height"] = "57%";
          break;
        case 90:
          this.audio.src = this.audioS[3];
          this.audio.play();
          this.b4.style["border-bottom-width"] = "1px";
          this.b4.style["height"] = "57%";
          break;
        case 85:
          this.audio.src = this.audioS[4];
          this.audio.play();
          this.b5.style["border-bottom-width"] = "1px";
          this.b5.style["height"] = "57%";
          break;
        case 79:
          this.audio.src = this.audioS[5];
          this.audio.play();
          this.b6.style["border-bottom-width"] = "1px";
          this.b6.style["height"] = "57%";
          break;

        case 65:
          this.audio.src = this.audioS[10];
          this.audio.play();
          this.w1.style["box-shadow"] =
            "inset 0 1px 0px rgba(255,255,255, 1),inset 0 -1px 0px rgba(255,255,255, 1),inset 1px 0px 0px rgba(255,255,255, 1),inset -1px 0px 0px rgba(255,255,255, 1),0 4px 3px rgba(0,0,0,0.7),inset 0 -1px 0px rgba(255,255,255, 1),inset 1px 0px 0px rgba(255,255,255, 1),inset -1px -1px 15px rgba(0,0,0, 1), -3px 4px 6px rgba(0,0,0, 0.5)";
          this.w1.style["border-bottom-width"] = "2px";
          break;
        case 83:
          this.audio.src = this.audioS[11];
          this.audio.play();
          this.w2.style["box-shadow"] =
            "inset 0 1px 0px rgba(255,255,255, 1),inset 0 -1px 0px rgba(255,255,255, 1),inset 1px 0px 0px rgba(255,255,255, 1),inset -1px 0px 0px rgba(255,255,255, 1),0 4px 3px rgba(0,0,0,0.7),inset 0 -1px 0px rgba(255,255,255, 1),inset 1px 0px 0px rgba(255,255,255, 1),inset -1px -1px 15px rgba(0,0,0, 1), -3px 4px 6px rgba(0,0,0, 0.5)";
          this.w2.style["border-bottom-width"] = "2px";
          this.w2.style["top"] = "-6px";
          break;
        case 68:
          this.audio.src = this.audioS[12];
          this.audio.play();
          this.w3.style["box-shadow"] =
            "inset 0 1px 0px rgba(255,255,255, 1),inset 0 -1px 0px rgba(255,255,255, 1),inset 1px 0px 0px rgba(255,255,255, 1),inset -1px 0px 0px rgba(255,255,255, 1),0 4px 3px rgba(0,0,0,0.7),inset 0 -1px 0px rgba(255,255,255, 1),inset 1px 0px 0px rgba(255,255,255, 1),inset -1px -1px 15px rgba(0,0,0, 1), -3px 4px 6px rgba(0,0,0, 0.5)";
          this.w3.style["border-bottom-width"] = "2px";
          this.w3.style["top"] = "-6px";
          break;
        case 70:
          this.audio.src = this.audioS[13];
          this.audio.play();
          this.w4.style["box-shadow"] =
            "inset 0 1px 0px rgba(255,255,255, 1),inset 0 -1px 0px rgba(255,255,255, 1),inset 1px 0px 0px rgba(255,255,255, 1),inset -1px 0px 0px rgba(255,255,255, 1),0 4px 3px rgba(0,0,0,0.7),inset 0 -1px 0px rgba(255,255,255, 1),inset 1px 0px 0px rgba(255,255,255, 1),inset -1px -1px 15px rgba(0,0,0, 1), -3px 4px 6px rgba(0,0,0, 0.5)";
          this.w4.style["border-bottom-width"] = "2px";
          this.w4.style["top"] = "-6px";
          break;
        case 71:
          this.audio.src = this.audioS[14];
          this.audio.play();
          this.w5.style["box-shadow"] =
            "inset 0 1px 0px rgba(255,255,255, 1),inset 0 -1px 0px rgba(255,255,255, 1),inset 1px 0px 0px rgba(255,255,255, 1),inset -1px 0px 0px rgba(255,255,255, 1),0 4px 3px rgba(0,0,0,0.7),inset 0 -1px 0px rgba(255,255,255, 1),inset 1px 0px 0px rgba(255,255,255, 1),inset -1px -1px 15px rgba(0,0,0, 1), -3px 4px 6px rgba(0,0,0, 0.5)";
          this.w5.style["border-bottom-width"] = "2px";
          this.w5.style["top"] = "-6px";
          break;
        case 72:
          this.audio.src = this.audioS[15];
          this.audio.play();
          this.w6.style["box-shadow"] =
            "inset 0 1px 0px rgba(255,255,255, 1),inset 0 -1px 0px rgba(255,255,255, 1),inset 1px 0px 0px rgba(255,255,255, 1),inset -1px 0px 0px rgba(255,255,255, 1),0 4px 3px rgba(0,0,0,0.7),inset 0 -1px 0px rgba(255,255,255, 1),inset 1px 0px 0px rgba(255,255,255, 1),inset -1px -1px 15px rgba(0,0,0, 1), -3px 4px 6px rgba(0,0,0, 0.5)";
          this.w6.style["border-bottom-width"] = "2px";
          this.w6.style["top"] = "-6px";
          break;
        case 74:
          this.audio.src = this.audioS[16];
          this.audio.play();
          this.w7.style["box-shadow"] =
            "inset 0 1px 0px rgba(255,255,255, 1),inset 0 -1px 0px rgba(255,255,255, 1),inset 1px 0px 0px rgba(255,255,255, 1),inset -1px 0px 0px rgba(255,255,255, 1),0 4px 3px rgba(0,0,0,0.7),inset 0 -1px 0px rgba(255,255,255, 1),inset 1px 0px 0px rgba(255,255,255, 1),inset -1px -1px 15px rgba(0,0,0, 1), -3px 4px 6px rgba(0,0,0, 0.5)";
          this.w7.style["border-bottom-width"] = "2px";
          this.w7.style["top"] = "-6px";
          break;
        case 75:
          this.audio.src = this.audioS[17];
          this.audio.play();
          this.w8.style["box-shadow"] =
            "inset 0 1px 0px rgba(255,255,255, 1),inset 0 -1px 0px rgba(255,255,255, 1),inset 1px 0px 0px rgba(255,255,255, 1),inset -1px 0px 0px rgba(255,255,255, 1),0 4px 3px rgba(0,0,0,0.7),inset 0 -1px 0px rgba(255,255,255, 1),inset 1px 0px 0px rgba(255,255,255, 1),inset -1px -1px 15px rgba(0,0,0, 1), -3px 4px 6px rgba(0,0,0, 0.5)";
          this.w8.style["border-bottom-width"] = "2px";
          this.w8.style["top"] = "-6px";
          break;
      }
    },

    pianoStyle(event) {
      var x = event.keyCode;
      switch (x) {
        case 87:
          this.b1.style["border-bottom-width"] = "8px";
          this.b1.style["height"] = "55%";
          break;
        case 69:
          this.b2.style["border-bottom-width"] = "8px";
          this.b2.style["height"] = "55%";
          break;
        case 84:
          this.b3.style["border-bottom-width"] = "8px";
          this.b3.style["height"] = "55%";
          break;
        case 90:
          this.b4.style["border-bottom-width"] = "8px";
          this.b4.style["height"] = "55%";
          break;
        case 85:
          this.b5.style["border-bottom-width"] = "8px";
          this.b5.style["height"] = "55%";
          break;
        case 79:
          this.b6.style["border-bottom-width"] = "8px";
          this.b6.style["height"] = "55%";
          break;

        case 65:
          this.w1.style["box-shadow"] =
            "inset 0 1px 0px rgba(255,255,255, 1),inset 0 -1px 0px rgba(255,255,255, 1),inset 1px 0px 0px rgba(255,255,255, 1),inset -1px 0px 0px rgba(255,255,255, 1),0 4px 3px rgba(0,0,0,0.7),inset 0 -1px 0px rgba(255,255,255, 1),inset 1px 0px 0px rgba(255,255,255, 1),inset -1px -1px 15px rgba(0,0,0, 0.5), -3px 4px 6px rgba(0,0,0, 0.5)";
          this.w1.style["border-bottom-width"] = "8px";
          break;
        case 83:
          this.w2.style["box-shadow"] =
            "inset 0 1px 0px rgba(255,255,255, 1),inset 0 -1px 0px rgba(255,255,255, 1),inset 1px 0px 0px rgba(255,255,255, 1),inset -1px 0px 0px rgba(255,255,255, 1),0 4px 3px rgba(0,0,0,0.7),inset 0 -1px 0px rgba(255,255,255, 1),inset 1px 0px 0px rgba(255,255,255, 1),inset -1px -1px 15px rgba(0,0,0, 0.5), -3px 4px 6px rgba(0,0,0, 0.5)";
          this.w2.style["border-bottom-width"] = "8px";
          break;
        case 68:
          this.w3.style["box-shadow"] =
            "inset 0 1px 0px rgba(255,255,255, 1),inset 0 -1px 0px rgba(255,255,255, 1),inset 1px 0px 0px rgba(255,255,255, 1),inset -1px 0px 0px rgba(255,255,255, 1),0 4px 3px rgba(0,0,0,0.7),inset 0 -1px 0px rgba(255,255,255, 1),inset 1px 0px 0px rgba(255,255,255, 1),inset -1px -1px 15px rgba(0,0,0, 0.5), -3px 4px 6px rgba(0,0,0, 0.5)";
          this.w3.style["border-bottom-width"] = "8px";
          break;
        case 70:
          this.w4.style["box-shadow"] =
            "inset 0 1px 0px rgba(255,255,255, 1),inset 0 -1px 0px rgba(255,255,255, 1),inset 1px 0px 0px rgba(255,255,255, 1),inset -1px 0px 0px rgba(255,255,255, 1),0 4px 3px rgba(0,0,0,0.7),inset 0 -1px 0px rgba(255,255,255, 1),inset 1px 0px 0px rgba(255,255,255, 1),inset -1px -1px 15px rgba(0,0,0, 0.5), -3px 4px 6px rgba(0,0,0, 0.5)";
          this.w4.style["border-bottom-width"] = "8px";
          break;
        case 71:
          this.w5.style["box-shadow"] =
            "inset 0 1px 0px rgba(255,255,255, 1),inset 0 -1px 0px rgba(255,255,255, 1),inset 1px 0px 0px rgba(255,255,255, 1),inset -1px 0px 0px rgba(255,255,255, 1),0 4px 3px rgba(0,0,0,0.7),inset 0 -1px 0px rgba(255,255,255, 1),inset 1px 0px 0px rgba(255,255,255, 1),inset -1px -1px 15px rgba(0,0,0, 0.5), -3px 4px 6px rgba(0,0,0, 0.5)";
          this.w5.style["border-bottom-width"] = "8px";
          break;
        case 72:
          this.w6.style["box-shadow"] =
            "inset 0 1px 0px rgba(255,255,255, 1),inset 0 -1px 0px rgba(255,255,255, 1),inset 1px 0px 0px rgba(255,255,255, 1),inset -1px 0px 0px rgba(255,255,255, 1),0 4px 3px rgba(0,0,0,0.7),inset 0 -1px 0px rgba(255,255,255, 1),inset 1px 0px 0px rgba(255,255,255, 1),inset -1px -1px 15px rgba(0,0,0, 0.5), -3px 4px 6px rgba(0,0,0, 0.5)";
          this.w6.style["border-bottom-width"] = "8px";
          break;
        case 74:
          this.w7.style["box-shadow"] =
            "inset 0 1px 0px rgba(255,255,255, 1),inset 0 -1px 0px rgba(255,255,255, 1),inset 1px 0px 0px rgba(255,255,255, 1),inset -1px 0px 0px rgba(255,255,255, 1),0 4px 3px rgba(0,0,0,0.7),inset 0 -1px 0px rgba(255,255,255, 1),inset 1px 0px 0px rgba(255,255,255, 1),inset -1px -1px 15px rgba(0,0,0, 0.5), -3px 4px 6px rgba(0,0,0, 0.5)";
          this.w7.style["border-bottom-width"] = "8px";
          break;
        case 75:
          this.w8.style["box-shadow"] =
            "inset 0 1px 0px rgba(255,255,255, 1),inset 0 -1px 0px rgba(255,255,255, 1),inset 1px 0px 0px rgba(255,255,255, 1),inset -1px 0px 0px rgba(255,255,255, 1),0 4px 3px rgba(0,0,0,0.7),inset 0 -1px 0px rgba(255,255,255, 1),inset 1px 0px 0px rgba(255,255,255, 1),inset -1px -1px 15px rgba(0,0,0, 0.5), -3px 4px 6px rgba(0,0,0, 0.5)";
          this.w8.style["border-bottom-width"] = "8px";
          break;
      }
    },
  },
};
</script>

<style scoped>
.morediv {
  background: white;
  margin-top: 30px;
  height: 100%;
}
.more {
  padding: 10px 50px;
  color: black;
  text-decoration: none;
}
</style>
