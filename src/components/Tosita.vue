<template>
  <div class="tosita_container" @click="handlePlay">
    <div v-if="!showModal" class="finger_container">
      <h1>Presiona aquí, tengo algo muy importante que decirte</h1>
      <img id="finger" src="../assets/finger.png" alt="" />
    </div>

    <div class="image_container" @click="showModal = !showModal">
      <img class="marco" src="../assets/marco2.png" alt="" />
      <div class="photo_container">
        <img class="photo" src="../assets/love.jpg" alt="" />
      </div>
      <transition name="fade">
        <div v-if="showModal" class="modal_container">
          <div class="msg_container">
            <p>{{ msg }}</p>
          </div>
        </div>
      </transition>
    </div>
  </div>
</template>
<script>
import sound from "../music/track.mp3";
export default {
  data() {
    return {
      showModal: false,
    };
  },
  setup() {
    let audio = new Audio(sound); // path to file
    const handlePlay = () => {
      audio.play();
    };
    let msg =
      "Hola mi tosita de amor.\n\n Quiero que sepas que me importas como no tienes idea, eres el principal motivo de mis alegrias por las mañanas, eres el principal motivo de mis pensamientos por las tardes y eres mi mayor felicidad por las noches.\n\n Quiero repetirte una y un billón de veces que eres el amor de mi vida y que jamás en la vidad tendre una mejor elección. \n Amor, sé y confio en Dios que vamos a estar juntos , que compartiremos una vida juntos y que seremos los mejor juntos porque somos una pareja increible , llena de amor , llena de respeto y se que seremos una pareja llena de confianza. \n\n TE AMOOO GRIMANEZA GARCIA";

    return {
      msg,
      handlePlay,
    };
  },
};
</script>
<style>
.tosita_container {
  margin: auto;
  width: 380px;
  height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;
  position: relative;
}
.image_container {
  display: flex;
  justify-content: center;
  align-items: center;
  position: relative;
  width: 380px;
  height: 500px;
  border-radius: 8px;
  background: rgba(255, 255, 255, 0.158);
  z-index: 50;
  cursor: pointer;
}
.marco {
  position: absolute;
  width: 100%;
  height: 380px;
  z-index: 100;
}
.photo_container {
  position: absolute;
  width: 191px;
  height: 188px;
  background: red;
}
.photo {
  width: 100%;
  height: 100%;
  background-position: center;
  background-repeat: no-repeat;
  background-size: cover;
}
.modal_container {
  position: absolute;
  display: flex;
  justify-content: center;
  align-items: center;
  width: 380px;
  height: 500px;
  background: #ffffff;
  z-index: 150;
  padding: 10px;
  border-radius: 8px;
  background: url("https://static.vecteezy.com/system/resources/previews/003/366/088/large_2x/old-paper-on-the-wood-background-ancient-scroll-free-photo.jpg")
    no-repeat center center/cover;
  transition: all 0.4;
}
.msg_container {
  width: 100%;
  height: 100%;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
}
.msg_container p {
  width: 100%;
  word-wrap: break-word;
  white-space: break-spaces;
  line-height: 23px;
  font-family: "Dancing Script", cursive;
  font-size: 20px;
}
.fade.enter {
  transition: opacity 0.5;
}
.fade-enter-active,
.fade-leave-active {
  transition: opacity 0.5s;
}
.fade-enter, .fade-leave-to /* .fade-leave-active below version 2.1.8 */ {
  opacity: 0;
}
.finger_container {
  position: absolute;
  width: 100%;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  top: 6px;
}
.finger_container h1 {
  font-size: 36px;

  text-align: center;
  border-radius: 6px;
  font-family: "Poppins", sans-serif;
}
#finger {
  width: 100px;
  height: 100px;
  transform: rotate(180deg);
}
</style>
