<template>
  <div id="home-view" class="view flex-box">
    <Header />
    <div class="body flex-box">
      <div class="section-1 flex-box">
        <div class="section-1-1 flex-box">
          <div class="image">
            <img src="https://github.com/muazhari/muazhari/blob/main/coding.gif?raw=true" />
          </div>
        </div>
        <div class="section-1-2 flex-box">
          <div class="title">Muhammad Kharisma Azhari</div>
          <div class="sub-title">Software Engineer</div>
          <div class="content">Yes, come here! Good for you! 🥳</div>
        </div>
      </div>
      <div class="section-2 flex-box">
        <div class="title flex-box">Reach me in there!</div>
        <div class="content flex-box">
          <!-- <div class="email flex-box">
            <a href="mailto: " target="_blank">
              <img
                src="https://cdn-icons.flaticon.com/png/512/542/premium/542638.png?token=exp=1647629230~hmac=3551e0925072d49a2cb3c7692aaf184c"
              />
            </a>
          </div> -->
          <div class="github flex-box">
            <a href="https://github.com/muazhari" target="_blank">
              <img src="https://cdn-icons-png.flaticon.com/512/1051/1051326.png" />
            </a>
          </div>
          <div class="linkedin flex-box">
            <a href="https://www.linkedin.com/in/muazhari" target="_blank">
              <img src="https://cdn-icons-png.flaticon.com/512/1384/1384088.png" />
            </a>
          </div>
        </div>
      </div>

      <div class="section-3 flex-box">
        <div class="title flex-box">Projects</div>
        <div class="content flex-box">
          <div
            class="card flex-box"
            v-for="project in projects"
            v-bind:key="project"
            v-on:click="redirect(project.url)"
          >
            <img
              v-bind:src="`https://api.apiflash.com/v1/urltoimage?access_key=2a5a11c5f6964c2b9d43331d8040e24f&url=${project.url}`"
              class="card-img-top"
            />
            <div class="card-body">
              <h5 class="card-title">{{ project.name }}</h5>
              <p class="card-text">
                {{ project.description }}
              </p>
            </div>
          </div>
        </div>
      </div>
    </div>
    <Footer />
  </div>
</template>

<script>
// import Header from "@/components/HeaderComponent.vue";
// import Footer from "@/components/FooterComponent.vue";
import { defineComponent } from "vue";

export default defineComponent({
  name: "HomeView",
  data: function () {
    return {
      projects: [
        {
          url: "https://github.com/sg-university/ventry-frontend",
          name: "Ventry - Frontend User",
          description:
            "Ventry App Frontend for user interaction using react.js. This project was created together as a team for University Tasks.",
        },
        {
          url: "https://github.com/sg-university/ventry-backend-management",
          name: "Ventry - Backend Management",
          description:
            "Ventry App Backend for management features using node.js. This project was created together as a team for University Tasks.",
        },
        {
          url: "https://github.com/sg-university/ventry-backend-forecast-2",
          name: "Ventry - Backend Forecasting",
          description:
            "Ventry App Backend for forecasting feature using django. This project was created together as a team for University Tasks.",
        },
        {
          url: "https://github.com/muazhari/fep-bot",
          name: "FEP Bot - Line Bot (Unofficial)",
          description:
            "Chat bot using LINE bot web hook API and node.js. This project was created independently.",
        },
        {
          url: "https://github.com/OLTeam-go/sea-store-backend-users",
          name: "SEA Store - Backend User",
          description:
            "SEA Store App Backend for users services using Spring Boot. This project was created together as a team in Compfest 12 Software Engineering Academy Event.",
        },
      ],
    };
  },
  methods: {
    redirect: function (url) {
      window.open(url, "_blank");
    },
  },
});
</script>

// style the html using saas
<style lang="scss">
#home-view {
  color: white;
  background: black;

  .body {
    .section-1 {
      margin: 20vh 10vh 5vh 10vh;
      flex-flow: row;
      .section-1-1 {
        margin: 0 5vh 0 0vh;
        .image {
          img {
            width: 30vh;
            height: 30vh;
            object-fit: cover;
            border-radius: 50%;
          }
        }
      }
      .section-1-2 {
        .title {
          font-weight: bold;
          font-size: 10vh;
        }
        .sub-title {
          color: #00eeff;
          font-size: 5vh;
        }
        .description {
          color: #6e6e6e;
          font-size: 5vh;
        }
      }
    }
    .section-2 {
      margin: 5vh 10vh 18vh 10vh;
      .content {
        flex-flow: row;
      }
      .email,
      .github,
      .linkedin {
        margin: 0 2vh 0 2vh;
        a {
          color: white;
          text-decoration: none;
          font-size: 5vh;
        }
        img {
          width: 5vh;
          height: 5vh;
          -webkit-filter: invert(1);
          filter: invert(1);
        }
      }
    }
    .section-3 {
      background: #181818;
      padding: 10vh 10vh 10vh 10vh;

      .title {
        font-weight: bold;
        font-size: 8vh;
        margin: 0vh 0vh 5vh 0vh;
      }

      .content {
        flex-flow: row wrap;
        .card {
          width: 50vh;
          height: 80vh;
          margin: 3vh 3vh 3vh 3vh;
          padding: 2vh 2vh 2vh 2vh;
          background: black;
          border-radius: 2%;
          box-shadow: 0 0 0.1vh 0.1vh #575757;

          &:hover {
            transform: scale(1.03);
            cursor: pointer;
            transition: all 0.15s ease-in-out;
            filter: brightness(1.01);
          }

          .card-body {
            padding: 2vh 1vh 1vh 1vh;
          }
          .card-title {
            font-size: 5vh;
            font-weight: bold;
          }
          .card-text {
            font-size: 3vh;
          }
        }
      }
    }
  }
}
</style>
