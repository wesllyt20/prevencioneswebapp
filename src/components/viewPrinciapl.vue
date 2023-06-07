<template>
  <v-app>
    <!-- START HEADER -->
    <!-- SUPERIOR -->
    <div class="barra-superior">
      <div class="logos">
        <v-img
          id="minam"
          src="https://www.igp.gob.pe/programas-de-investigacion/images/logo-minan.png"
        />
        <v-img
          id="igpLogo"
          src="https://www.igp.gob.pe/programas-de-investigacion/images/logo_igp_normal.png"
        />
      </div>
      <div id="dividermenutop" class="border border-vertical" />
      <h1 class="titulo">
        Monitoreo de la vegetación para la prevención de incendios forestales
      </h1>

      <div class="opciones">
        <a
          id="acerca"
          class="my-linktop"
          @click="btnGeofi()"
          :class="{ 'my-linktop': true, active: mostrarGeo }"
          >Acerca de</a
        >
        <div id="dividermenutopL" class="border border-vertical" />

        <a
          id="func"
          class="my-linktop"
          @click="btnFuncion()"
          :class="{ 'my-linktop': true, active: mostrarFun }"
          >Guía de uso</a
        >
        <div id="dividermenutopL" class="border border-vertical" />

        <a
          id="contacto"
          class="my-linktop"
          @click="btnCont()"
          :style="{ marginRight: '50px' }"
          :class="{ 'my-linktop': true, active: mostrarCont }"
          >Contacto</a
        >
      </div>

      <button class="menu-btn" @click="toggleMenu">
        <svg
          fill="#65696c"
          width="24px"
          height="24px"
          viewBox="0 0 32.00 32.00"
          version="1.1"
          xmlns="http://www.w3.org/2000/svg"
          stroke="#65696c"
          style="margin-top: 10px"
        >
          <g id="SVGRepo_bgCarrier" stroke-width="0"></g>
          <g
            id="SVGRepo_tracerCarrier"
            stroke-linecap="round"
            stroke-linejoin="round"
          ></g>
          <g id="SVGRepo_iconCarrier">
            <path
              d="M0.844 6.050c-0.256-0.256-0.381-0.581-0.381-0.975s0.125-0.719 0.381-0.975 0.581-0.381 0.975-0.381h28.512c0.394 0 0.719 0.125 0.975 0.381s0.381 0.581 0.381 0.975-0.125 0.719-0.381 0.975-0.581 0.381-0.975 0.381h-28.512c-0.394 0-0.719-0.125-0.975-0.381zM31.306 14.963c0.256 0.256 0.381 0.581 0.381 0.975s-0.125 0.719-0.381 0.975-0.581 0.381-0.975 0.381h-28.512c-0.394 0-0.719-0.125-0.975-0.381s-0.381-0.581-0.381-0.975 0.125-0.719 0.381-0.975 0.581-0.381 0.975-0.381h28.512c0.394 0 0.719 0.125 0.975 0.381zM31.306 25.819c0.256 0.256 0.381 0.581 0.381 0.975s-0.125 0.719-0.381 0.975-0.581 0.381-0.975 0.381h-28.512c-0.394 0-0.719-0.125-0.975-0.381s-0.381-0.581-0.381-0.975 0.125-0.719 0.381-0.975 0.581-0.381 0.975-0.381h28.512c0.394 0 0.719 0.131 0.975 0.381z"
            ></path>
          </g>
        </svg>
      </button>

      <div v-if="showMenu" class="dropdown-menu">
        <ul>
          <li>
            <a
              id="acerca"
              @click="
                btnGeofi();
                closeMenu();
              "
              :class="{ 'my-linktop': true, active: mostrarGeo }"
              >Acerca de</a
            >
          </li>
          <li>
            <a
              id="func"
              @click="
                btnFuncion();
                closeMenu();
              "
              :class="{ 'my-linktop': true, active: mostrarFun }"
              >Guía de uso</a
            >
          </li>
          <li>
            <a
              id="contacto"
              @click="
                btnCont();
                closeMenu();
              "
              :class="{ 'my-linktop': true, active: mostrarCont }"
              >Contacto</a
            >
          </li>
        </ul>
      </div>
    </div>

    <!-- final superior -->
    <!-- INFERIOR -->
    <div class="barra-inferior">
      <a
        class="my-link"
        href="https://www.gob.pe/igp"
        target="_blank"
        :style="{ marginLeft: '48px' }"
      >
        <span class="link-text">
          <svg
            class="mi-svg"
            width="18px"
            height="18px"
            viewBox="0 0 24.00 24.00"
            xmlns="http://www.w3.org/2000/svg"
            fill="#211d18"
            style="vertical-align: middle; margin-right: 4px"
          >
            <g id="SVGRepo_bgCarrier" stroke-width="0"></g>
            <g
              id="SVGRepo_tracerCarrier"
              stroke-linecap="round"
              stroke-linejoin="round"
            ></g>
            <g id="SVGRepo_iconCarrier">
              <rect x="0" fill="none" width="24" height="24"></rect>
              <g>
                <path
                  d="M22 9L12 1 2 9v2h2v10h5v-4c0-1.657 1.343-3 3-3s3 1.343 3 3v4h5V11h2V9z"
                ></path>
              </g>
            </g>
          </svg>Portal IGP</span
        >
      </a>

      <div id="dividermenubot" class="border border-vertical" />
      <a
        class="my-link"
        href="https://www.igp.gob.pe/servicios/infraestructura-de-datos-espaciales/"
        target="_blank"
        >Infraestructura de datos espaciales (IDE - IGP)</a
      >
      <div id="dividermenubot" class="border border-vertical" />
      <a
        class="my-link"
        href="https://www.igp.gob.pe/servicios/infraestructura-de-datos-espaciales/componentes/visor-geografico"
        target="_blank"
        >Visor Geográfico</a
      >
      <div id="dividermenubot" class="border border-vertical" />
      <span class="my-link" style="color: #0000af; text-decoration: none"
        >Monitoreo NDVI</span
      >
    </div>
    <!-- final inferior -->
    <!-- EMD HEADER -->

    <!-- START MENU -->
    <!-- boton -->
    <div v-if="showVButton" class="tooltip">
      <v-btn
        id="btnFlecha"
        class="rail-variant ml-n9"
        :class="{ 'rail-variant--open': drawer, 'bounce-right': isLoaded }"
        icon
        @click.stop="onMoveWidgetsButtonClick"
      >
        <v-img
          id="iconFlecha"
          class="rotate-image"
          :class="{ 'rotate-180': !drawer }"
          src="https://i.ibb.co/CJzYHCM/Vector-1.png"
        ></v-img>
        <!--https://i.ibb.co/VSqBM9X/Vector-1.png →→→→ -->
        <span class="tooltiptext">{{ tooltipText }}</span>
      </v-btn>
    </div>
    <!-- contenedor de menu -->
    <v-navigation-drawer
      class="vNavi"
      v-model="drawer"
      :scrim="false"
      hide-overlay
      :style="{
        transition: 'transform 0.01s ease-in-out',
        width: anchoMenu,
        marginTop: marginTopNav,
      }"
    >
      <div
        class="cerrarAside"
        style="
          position: absolute;
          top: 0;
          right: 0;
          margin: 5px 15px;
          cursor: pointer;
        "
        @click="drawer = false"
      >
        <a
          style="
            color: #20aaff;
            font-weight: bold;
            font-size: 15px;
            position: relative;
          "
        >
          <span
            style="
              position: absolute;
              top: 6px;
              right: 6px;
              width: 20px;
              height: 20px;
              background-color: white;
              border-radius: 50%;
              border: 1px solid #0000;
              box-shadow: -0.839103px 1.67821px 3.35641px rgba(0, 0, 0, 0.6);
              display: flex;
              justify-content: center;
              align-items: center;
            "
          >
            <span style="position: relative">x</span>
          </span>
        </a>
      </div>
      <contFuncion v-show="mostrarFun"></contFuncion>
      <contGeofisico v-show="mostrarGeo"></contGeofisico>
      <contContacto v-show="mostrarCont"></contContacto>
      <contListado v-show="mostrarList"></contListado>
    </v-navigation-drawer>
    <!-- END MENU -->

    <!-- START IFRAME -->
    <div id="contenedor" style="">
      <iframe
        id="inlineFrameExample"
        src="https://ide.igp.gob.pe/geovisor/estudios-ndvi/"
        style="width: 100%; height: 100%; border: 0"
        @load="iframeLoad"
      ></iframe>
    </div>
    <!-- END IFRAME -->
  </v-app>
</template>

<script>
import contFuncion from "./contFuncion.vue";
import contGeofisico from "./contGeofisico.vue";
import contContacto from "./contContacto.vue";
import contListado from "./contListado.vue";

window.onload = function () {
  var iframe = document.getElementById("inlineFrameExample");
  var container = document.getElementById("contenedor");
  iframe.onload = function () {
    container.style.height =
      iframe.contentWindow.document.body.scrollHeight + "px";
  };
};
const ids = [
  "widgets_ZoomSlider_Widget_72",
  "widgets_HomeButton_Widget_68",
  "dijit__WidgetBase_0",
  "_62_panel",
  "widgets_Scalebar_Widget_59",
  "widgets_Coordinate_Widget_61",
];

export default {
  name: "viewPrincipal",

  components: {
    contFuncion,
    contGeofisico,
    contContacto,
    contListado,
  },
  data() {
    return {
      railVariantLeft: 10,
      drawer: false,
      mostrarGeo: false,
      mostrarFun: false,
      mostrarCont: false,
      mostrarList: false,
      anchoMenu: "450px",
      marginTopNav: null,
      elementos: false,
      indexflecha: -1,
      showMenu: false,
      isLoaded: false,
      showVButton: false,
      tooltipText: "¡Cierra aquí!",
      accionTooltip: "visible",
      widTooltip: "150px",
    };
  },

  mounted() {
    window.addEventListener("resize", this.ajustarMargenTop);
    if (window.innerWidth <= 1690) {
      //AQUI PUEDE ENTRAR EL ANCHO DEL ASIDE
      this.marginTopNav = "80px";
    } else {
      this.marginTopNav = "120px";
    }
  },
  beforeUnmount() {
    window.removeEventListener("resize", this.ajustarMargenTop);
  },
  methods: {
    toggleMenu() {
      this.showMenu = !this.showMenu;
    },
    closeMenu() {
      this.showMenu = false;
    },

    ajustarMargenTop() {
      if (window.innerWidth <= 1690) {
        //AQUI PUEDE ENTRAR EL ANCHO DEL ASIDE
        this.marginTopNav = "80px";
      } else {
        this.marginTopNav = "120px";
      }
    },
    iframeLoad() {
      setTimeout(() => {
        this.drawer = true;
        this.mostrarGeo = true;
        this.indexflecha = 1;
        this.isLoaded = true;
        this.showVButton = true;
        setTimeout(() => {
          this.tooltipText = "¡Cierra aquí!";
          setTimeout(() => {
            this.accionTooltip = "hidden";
          }, 3000);
        }, 1000);
      }, 4000);
    },
    btnGeofi() {
      this.ocultarTodo();
      this.mostrarGeo = true;
      },
    btnCont() {
      this.ocultarTodo();
      this.mostrarCont = true;
  
    },
    btnListado() {
      this.ocultarTodo();
      this.mostrarList = true;
   
    },
    btnFuncion() {
      this.ocultarTodo();
      this.mostrarFun = true;

    },

    ocultarTodo() {
      this.mostrarGeo = false;
      this.mostrarFun = false;
      this.mostrarCont = false;
      this.mostrarList = false;
      this.drawer = true;
    },
    ocultarTodo2() {
      this.mostrarGeo = false;
      this.mostrarFun = false;
      this.mostrarCont = false;
      this.mostrarRequi = false;
    },

    onMoveWidgetsButtonClick() {
      this.drawer = !this.drawer;

      if (this.drawer === false) {
        this.ocultarTodo2();
      } else if (this.drawer === true) {
        this.mostrarGeo = true;
      }
    },
    movewidgets(displacement) {
      const iframe = document.getElementById("inlineFrameExample");
      const idocument = iframe.contentWindow.document;

      ids.forEach((id) => {
        var widget = null;
        while (!widget) {
          widget = idocument.getElementById(id);
        }
        let left = 0;
        if (!widget.style.inset) {
          left = parseInt(widget.style.left.slice(0, 3));
          widget.style.left = `${left + displacement}px`;
        } else {
          let split = widget.style.inset.split(" ");
          left = parseInt(split[3].slice(0, 3));
          split[3] = `${left + displacement}px`;
          widget.style.inset = split.join(" ");
        }
      });
    },
  },
  watch: {
    drawer(val) {
      this.railVariantLeft = val ? 260 : 10;

      if (val === true) {
        this.tooltipText = "¡Cierra aquí!";
        this.widTooltip = "150px";
        this.movewidgets(465);

        if (
          this.mostrarCont === false &
          this.mostrarFun === false &
          this.mostrarGeo === false
        ) {
          this.mostrarGeo = true;
        }
      } else if (val === false) {
        this.tooltipText = "¡Abre aquí!";
        this.widTooltip = "140px";
        this.movewidgets(-465);
        this.mostrarGeo = false;
      }
      console.log(val);
    },
  },
};
</script>

<style scoped>
* {
  font-family: "Poppins", sans-serif;
}
#contenedor {
  height: auto;
  position: absolute;
  top: 120px;
  left: 0;
  right: 0;
  bottom: 0;
  overflow: hidden;
}
.bounce-right {
  animation: bounce-right 0.8s linear both;
}

@keyframes bounce-right {
  0% {
    transform: translateX(48px);
    animation-timing-function: ease-in;
    opacity: 1;
  }
  24% {
    opacity: 1;
  }
  40% {
    transform: translateX(26px);
    animation-timing-function: ease-in;
  }
  65% {
    transform: translateX(13px);
    animation-timing-function: ease-in;
  }
  82% {
    transform: translateX(6.5px);
    animation-timing-function: ease-in;
  }
  93% {
    transform: translateX(4px);
    animation-timing-function: ease-in;
  }
  25%,
  55%,
  75%,
  87%,
  98% {
    transform: translateX(0);
    animation-timing-function: ease-out;
  }
  100% {
    transform: translateX(0);
    animation-timing-function: ease-out;
    opacity: 1;
  }
}
/* CONTENEDOR  */
.fill-height {
  height: 100vh;
  margin-top: 120px;
}

.rail-variant {
  position: absolute;
  top: 0;
  left: 0;
  z-index: 2;
  transition: left 0.01s ease-in-out;
}

.rail-variant--open {
  left: calc(v-bind(anchoMenu) + 3px);
}
/* BOTON DE FLECHA */
#btnFlecha {
  margin-top: 12.5rem;
  position: absolute;
  width: 55px;
  height: 55px;
  z-index: v-bind(indexflecha);
  border-radius: 0% 100% 100% 0%;
}
#iconFlecha {
  margin-left: 30px;
  width: 20px;
  height: 19px;
}
/* HEADER SUPERIOR */
.barra-superior {
  display: flex;
  align-items: center;
  justify-content: space-between;
  height: 80px;
  background: #ffffff;
  left: 0px;
  top: 0px;
}

.logos {
  display: flex;
  align-items: center;
  padding-left: 20px;
}

#minam {
  width: 157.49px;
  height: 46px;
  margin-right: 10px;
}

#igpLogo {
  width: 122px;
  height: 40px;
}
#dividermenutop {
  height: 40%;
  margin-left: 25px;
  margin-right: 25px;
}
.titulo {
  color: #0000af;
  font-style: normal;
  font-weight: 300;
  font-size: 24px;
  line-height: 36px;
}

.opciones {
  display: flex;
  margin-left: auto;
}

.opciones span {
  padding: 0 8px;
}

.opciones span {
  padding: 0 8px;
}

.my-linktop {
  color: #211d18; /* color del enlace */
  font-style: normal;
  font-weight: 500;
  font-size: 16px;
  line-height: 24px;
}

.my-linktop:hover {
  color: #0000af;
}

.my-linktop:active {
  color: #0000af;
}
.my-linktop:link {
  color: #737b80;
  text-decoration: none;
}
.my-linktop.active {
  color: #0000af;
  pointer-events: none; /* Evita que se pueda hacer clic en el enlace */
  cursor: default; /* Cambia el cursor a "predeterminado" para indicar que no se puede hacer clic */
}

#dividermenutopL {
  color: #211d18;
  margin-top: 4px;
  height: 16px;
  margin-left: 10px;
  margin-right: 10px;
}
/* HEADER INFERIOR */
.barra-inferior {
  display: flex;
  align-items: center;
  box-sizing: border-box;
  background: rgba(214, 214, 227, 0.1);
  border-width: 1px 0px;
  border-style: solid;
  border-color: #d6d6e3;
  height: 40px;
}

/* botones link */
.my-link {
  color: #211d18; 
  text-decoration: none;
  margin-right: 1rem;
  font-weight: 300;
  font-size: 12px;
}
.my-link:link {
  color: #737b80;
  text-decoration: none;
  margin-right: 1rem;
}

.my-link:active {
  color: #0000af;
}

.link-text:hover,
.my-link:hover,
.link-text:hover .mi-svg {
  color: #0000af !important;
  fill: #0000af !important;
  text-decoration: underline;
}
#dividermenubot {
  color: #211d18;
  height: 40%;
  margin-left: 5px;
  margin-right: 15px;
}
.rotate-image {
  transition: transform 0.5s; /* Agrega transición de transformación */
}

.rotate-image.rotate-180 {
  transform: rotate(180deg);
}
.menu-btn {
  display: none; /* ocultar el botón en pantallas grandes */
  cursor: pointer;
  margin-right: 10px;
  padding: 0px 10px;
  border-radius: 10px;
  box-sizing: border-box;
  cursor: pointer;
  background: #ffffff;
  border: 0.566325px solid rgba(25, 32, 36, 0.6);
  border-radius: 3.39795px;
}
.menu-btn:active {
  filter: brightness(75%);
}
.dropdown-menu {
  position: absolute;
  margin: 245px 0 0 0;
  padding: 20px 0;
  right: 0;
  z-index: 2;

  background: var(--dropdown-background);
  border-radius: 6px;
  list-style: none;

  background-color: #fff;
  border: 1px solid #ccc;
  border-radius: 5px;
  box-shadow: 0 2px 4px rgba(0, 0, 0, 0.2);
  padding: 10px;
  z-index: 199999;
}
.dropdown-menu ul {
  list-style: none;
  margin: 0;
  padding: 0;
}
.dropdown-menu li {
  margin-bottom: 10px;
}

.dropdown-menu a {
  color: #333;
  text-decoration: none;
  padding: 5px;
  display: block;
}

.dropdown-menu a:hover {
  background-color: #f7f7f7;
}

.tooltip {
  position: relative;
  display: inline-block;
}

.tooltip .tooltiptext {
  visibility: v-bind(accionTooltip);
  width: v-bind(widTooltip);
  background: rgb(34, 209, 238);
  background: linear-gradient(
    90deg,
    rgba(34, 209, 238, 1) 0%,
    rgba(61, 90, 241, 1) 100%
  );
  text-transform: none;
  color: #fff;
  text-align: center;
  border-radius: 41.116px;
  padding: 5px 0;
  position: absolute;
  z-index: 1;
  top: 57%;
  left: 130%;
  margin-top: -20px;
  transition: opacity 0.3s ease-in-out;
  box-shadow: -0.839103px 1.67821px 3.35641px rgba(0, 0, 0, 0.6);
}

.tooltip:hover .tooltiptext {
  visibility: visible;
}
.cerrarAside {
  display: none;
}
@media screen and (max-width: 1690px) {
  .vNavi {
    margin-top: 80px !important;
  }
  .barra-superior {
    flex-wrap: wrap; /* para que los elementos se ajusten al ancho de la pantalla */
  }
  .titulo {
    margin-right: auto;
  }
  .menu-btn {
    display: block;
  }

  /* ocultar el menú principal en pantallas pequeñas */
  .opciones {
    display: none;
  }

  /* mostrar el menú desplegable en pantallas pequeñas */
  .dropdown-menu {
    display: block;
  }
  .barra-inferior {
    display: none;
  }
  #contenedor {
    top: 80px;
  }
}
@media screen and (max-width: 1341px) {
  .titulo,
  #dividermenutop {
    display: none;
  }
  .cerrarAside {
    display: block;
  }
  .tooltip:hover .tooltiptext {
    visibility: hidden;
  }
}
</style>
