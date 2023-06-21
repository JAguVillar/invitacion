<template>
  <section id="one">
    <div class="color1"></div>
    <div class="color2"></div>
    <div class="color3"></div>
    <div class="color4"></div>
    <div class="headerContainer clash bold">
      <div>!TE INVITO A MI</div>
      <div>CUMPLE!</div>
    </div>
    <div class="footer">
      <div class="item first">
        <div class="left clash bold">🗓️ ¿Cuándo?</div>
        <div class="right clash semibold">
          El domingo 25 de Junio, al mediodía.
        </div>
      </div>
      <div class="item second">
        <div class="left clash bold">📍 ¿Dónde?</div>
        <div class="right clash semibold">Mi finca.</div>
      </div>
      <div class="item third">
        <div class="left clash bold">📦 ¿Tengo que llevar algo?</div>
        <div class="right clash semibold">
          Lo que quieras tomar o cualquier cosa!
        </div>
      </div>
      <div class="item fourth">
        <div class="left clash bold">¿Cuál será el menú?</div>
        <div class="right clash semibold">
          Por ahora asadito 🥩, pero pueden ser pizzas 🍕.
        </div>
      </div>
      <div class="item fifth" @click="irA()">
        <div class="question clash bold">¿Tienes más preguntas?</div>
      </div>
    </div>
  </section>
  <section id="two" ref="two">
    <div class="clash bold faqTitle">Preguntas frecuentes</div>
    <div class="faq">
      <div class="faqItem">
        <div class="pregunta archivo bold">
          💙💛💙 ¿Se podrá ver la despedida de Riquelme?
        </div>
        <div class="respuesta archivo-regular">
          Sí, los que querramos ver tenemos tele.
        </div>
      </div>
      <div class="faqItem">
        <div class="pregunta archivo bold">
          🥩❌ Si no como/quiero asado, ¿habrá algo más?
        </div>
        <div class="respuesta archivo-regular">
          Creo que sí, cualquier cosita mandame un WhatsApp.
        </div>
      </div>
      <div class="faqItem">
        <div class="pregunta archivo bold">
          🍊 Es epoca de mandarinas, ¿habrán?
        </div>
        <div class="respuesta archivo-regular">Obvio.</div>
      </div>
      <div class="faqItem">
        <div class="pregunta archivo bold">🎁 ¿No sabes que regalarme?</div>
        <div class="respuesta archivo-regular">
          No te preocupes mi buen amigo, sé lo dificil que puede ser buscar un
          regalo 😔, ¡aquí tengo una
          <a
            class="archivo bold"
            target="_blank"
            href="https://regalame.app/jaguvillar/cumple-29-agoto"
          >
            listita
          </a>
          de regalos que me pueden gustar!
        </div>
      </div>
    </div>
    <div
      class="wapp clash semibold"
      @mouseenter="dentro()"
      @mouseleave="fuera()"
      @click="mandar()"
    >
      <span class="texto1">¿Tienes alguna otra pregunta?</span>
      <span class="texto2"
        >Haz clic para mandarme un mensaje
        <img
          src="./assets/Digital_Glyph_White.svg"
          style="width: 32px"
          alt=""
          srcset=""
          class="wappSvg"
        />
      </span>
    </div>
  </section>
</template>

<script>
import { gsap } from "gsap";
import CustomEase from "gsap/CustomEase";
import ScrollTrigger from "gsap/ScrollTrigger";
gsap.registerPlugin(ScrollTrigger);
gsap.registerPlugin(CustomEase);

export default {
  name: "BaseComponent",
  props: {},
  data() {
    return {};
  },
  mounted() {
    let tl = gsap.timeline();

    tl.to(".color1", { height: 0, duration: 0.9 });
    tl.to(".color2", { height: 0, duration: 0.9 });
    tl.to(".color3", { height: 0, duration: 0.9 });
    tl.to(".color4", { height: 0, duration: 0.9 });

    // tl.fromTo(
    //   ".letra1",
    //   { y: -100, opacity: 0 },
    //   { y: 0, opacity: 1, duration: 0.4 }
    // );
    // tl.fromTo(
    //   ".letra2",
    //   { y: -100, opacity: 0 },
    //   { y: 0, opacity: 1, duration: 0.4 }
    // );
    // tl.fromTo(
    //   ".letra3",
    //   { y: -100, opacity: 0 },
    //   { y: 0, opacity: 1, duration: 0.4 }
    // );
    // tl.fromTo(
    //   ".letra4",
    //   { y: -100, opacity: 0 },
    //   { y: 0, opacity: 1, duration: 0.4 }
    // );
    // tl.fromTo(
    //   ".admiracion",
    //   { y: -100, opacity: 0 },
    //   { y: 0, opacity: 1, duration: 0.4 }
    // );
  },
  computed: {},
  methods: {
    irA() {
      this.$refs.two.scrollIntoView({ behavior: "smooth" });
    },
    dentro() {
      let tl = gsap.timeline();
      tl.fromTo(".texto1", { opacity: 1 }, { opacity: 0, duration: 0.1 });
      tl.fromTo(".texto2", { opacity: 0 }, { opacity: 1, duration: 0.1 });
      tl.to(".wapp", { background: "#25d366", duration: 0.1 });
    },
    fuera() {
      let tl = gsap.timeline();
      tl.fromTo(".texto1", { opacity: 0 }, { opacity: 1, duration: 0 });
      tl.fromTo(".texto2", { opacity: 1 }, { opacity: 0, duration: 0.1 });
      tl.to(".wapp", { background: "#1c1b21" });
    },
    mandar() {
      let texto = "Hola Agoto, ";
      window.open(" https://wa.me/3855048767?" + texto, "_blank");
    },
  },
};
</script>

<style>
@import "./css/styles.css";

#app {
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #fff;

  overflow: hidden;
}

body {
  margin: 0px;
}
section#one {
  height: 100vh;
  background: #1c1b21;
  position: relative;
  height: 100vh;
}

.color1 {
  z-index: 5;
  position: absolute;
  top: 0;
  left: 0;
  width: 100vw;
  height: 100vh;
  background-color: #f3d2c1;
}
.color2 {
  z-index: 4;
  position: absolute;
  top: 0;
  left: 0;
  width: 100vw;
  height: 100vh;
  background-color: #f582ae;
}
.color3 {
  z-index: 3;
  position: absolute;
  top: 0;
  left: 0;
  width: 100vw;
  height: 100vh;
  background-color: #8bd3dd;
}
.color4 {
  z-index: 2;
  position: absolute;
  top: 0;
  left: 0;
  width: 100vw;
  height: 100vh;
  background-color: #f25f4c;
}

section#two {
  width: 100vw;
  height: 100vh;
  background-color: #1c1b21;
  position: relative;
}

.headerContainer {
  display: flex;
  justify-content: center;
  align-items: center;
  flex-direction: column;
  font-size: 85px;
  letter-spacing: 3px;
  height: 50%;
}

.footer {
  position: absolute;
  bottom: 0px;
  width: 100%;

  background: black;
}
.item {
  display: flex;
  height: 100px;
  width: 100%;
}

.item.first .left {
  background-color: #f3d2c1;
}
.item.second .left {
  background-color: #f582ae;
}
.item.third .left {
  background-color: #8bd3dd;
}
.item.third .left {
  background-color: #8bd3dd;
}
.item.fourth .left {
  background-color: #f25f4c;
}
.item.fifth {
  cursor: pointer;
  transition: 0.2s ease-in-out;
}
.item.fifth:hover {
  background: #fff;
  color: #1c1b21;
  cursor: pointer;
  transition: 0.2s ease-in-out;
}

.left {
  width: 30%;
  color: black;
  display: flex;
  justify-content: flex-end;
  align-items: center;
  font-size: 32px;
  padding-right: 20px;
}

.right {
  width: 70%;
  background-color: #28272f;
  display: flex;
  justify-content: flex-start;
  align-items: center;
  padding-left: 20px;
  font-size: 32px;
  letter-spacing: 2px;
}

.question {
  width: 100%;
  display: flex;
  justify-content: center;
  align-items: center;
  font-size: 32px;
  padding-right: 20px;
}

.faqTitle {
  font-size: 72px;
  padding: 20px 0px 0px 50px;
}

.faq {
  width: 100%;
  display: flex;
  flex-direction: column;
  padding: 20px 0px 0px 50px;
}

.faqItem {
  margin: 10px 0px;
}

.pregunta {
  font-size: 32px;
}
.respuesta {
  font-size: 24px;
  word-wrap: normal;
}

a {
  color: white;
}

a:hover {
  color: salmon;
}

a:visited {
  text-decoration: none;
}

.wapp {
  position: absolute;
  bottom: 0px;
  border-top: 1px solid #25d366;
}

.wapp {
  letter-spacing: 1px;
  height: 150px;
  width: 100%;
  display: flex;
  justify-content: center;
  align-items: center;
  cursor: pointer;
  cursor: url("data:image/svg+xml;utf8,<svg xmlns='http://www.w3.org/2000/svg'  width='60' height='68' viewport='0 0 200 200' style='fill:black;font-size:32px;'><text y='50%'>🤙</text></svg>")
      16 0,
    auto;
}

.texto1 {
  position: absolute;
  font-size: 36px;
}
.texto2 {
  position: absolute;
  opacity: 0;
  font-size: 36px;
  color: white;
  display: flex;
  justify-content: center;
  align-items: center;
}

.wappSvg {
  margin-left: 10px;
}
</style>
