<template>
  <div>
    <NavBar />
  </div>
  <div class="container">
    <div class="containercards">
      <div class="card__header"></div>
      <div class="card__body">
        <h1>Profile</h1>
        <div class="card__footer">
          <div style="display: inline" class="user__info">
            <img
              v-if="user.avatar == null"
              src="https://w7.pngwing.com/pngs/178/595/png-transparent-user-profile-computer-icons-login-user-avatars-thumbnail.png"
              alt="user avatar"
              class="user__image"
              style="height: 50px; width: 50px"
            />
            <img
              v-if="user.avatar != null"
              :src="user.avatar"
              alt="user avatar"
              class="user__image"
              style="height: 70px; width: 70px"
            />
          </div>
          <div class="card-body">
            <h5 class="card-title">
              <h3>{{ user.username }}</h3>
              <h3>{{ user.lastname }}</h3>
            </h5>
            <p class="card-text">From {{ user.country }}</p>
            Role : {{ user.role }}
            <h6>Email : {{ user.email }}</h6>
          </div>
          <div class="card__footer">
            <div style="display: inline" class="user__info">
              <div>
                <router-link :to="'/'"
                  ><button
                    href="#"
                    type="button"
                    id="crud"
                    class="btn btn-outline-dark"
                  >
                    Back
                  </button></router-link
                >
                <router-link :to="'/UpdateUser'"
                  ><button
                    href="#"
                    type="button"
                    id="crud"
                    class="btn btn-outline-dark"
                  >
                    Modify
                  </button></router-link
                >
                <!--<button
                  v-on:click.prevent="deleteUser(user)"
                  href="#"
                  type="button"
                  id="crud"
                  class="btn btn-outline-dark"
                >
                  Supprimer
                </button>-->
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
  <div><MapSelection /></div>
  <div class="tooltip-content">
    <p>{{ destination }}</p>
  </div>
  <div><MyTrips /></div>
  <div v-if="this.role == 'curateur' || 'admin'"><MyActivities /></div>
</template>

<script>
import axios from "axios";
import MyTrips from "../../components/MyTrips";
import MyActivities from "../../components/MyActivities";
import MapSelection from "@/components/MapSelection.vue";
import NavBar from "@/components/NavBar.vue";

export default {
  components: { 
    MyTrips, 
    MyActivities, 
    MapSelection, 
    NavBar
     },
  name: "profile",
  props: {
    id: "",
    username: "",
    lastname: "",
    email: "",
    role: "",
    select: [],
  },
  data: () => {
    return {
      user: {},
      id: "",
      token: "",
      role: "",
      destination: "",
      selector: "",
    };
  },
  mounted() {
    this.token = localStorage.getItem("token");
    this.id = localStorage.getItem("user_id");
    this.role = localStorage.getItem("role");
    axios
      .get("http://localhost:3020/users/" + this.id, {
        headers: {
          Authorization: `Bearer ${this.token}`,
        },
      })
      .then((response) => {
        console.log(response.data);
        this.user = response.data;
      });
  },
  methods: {
       showpop () {
      this.addpop = true
    },
    closepop () {
      this.addpop = false
    }
  }
};
</script>

<style scoped>
.user__image {
  border-radius: 50%;
  height: 100px;
}
@import url("https://fonts.googleapis.com/css2?family=Quicksand:wght@300..700&display=swap");
body {
  font-family: "Quicksand", sans-serif;
  display: grid;
  place-items: center;
  height: 100vh;
  background: #7f7fd5;
  background: linear-gradient(to right, #91eae4, #86a8e7, #7f7fd5);
}
.containercards {
  margin: auto;
  display: flex;
  flex-wrap: wrap;
  justify-content: center;
  max-width: 1200px;
  margin-block: 2rem;
  gap: 2rem;
}
img {
  max-width: 100%;
  display: block;
  object-fit: cover;
  margin-left: auto;
  margin-right: auto;
}
.card {
  display: flex;
  flex-direction: column;
  width: clamp(20rem, calc(20rem + 2vw), 15rem);
  overflow: hidden;
  box-shadow: 0 0.1rem 1rem rgba(0, 0, 0, 0.1);
  border-radius: 1em;
  background: #ece9e6;
  background: linear-gradient(to right, #ffffff, #ece9e6);
}
.card__body {
  padding: 1rem;
  display: flex;
  flex-direction: column;
  gap: 0.5rem;
}
.tag {
  align-self: flex-start;
  padding: 0.25em 0.75em;
  border-radius: 1em;
  font-size: 0.75rem;
}
.tag + .tag {
  margin-left: 0.5em;
}
.tag-blue {
  background: #56ccf2;
  background: linear-gradient(to bottom, #2f80ed, #56ccf2);
  color: #fafafa;
}
.tag-brown {
  background: #d1913c;
  background: linear-gradient(to bottom, #ffd194, #d1913c);
  color: #fafafa;
}
.tag-red {
  background: #cb2d3e;
  background: linear-gradient(to bottom, #ef473a, #cb2d3e);
  color: #fafafa;
}
.card__body h4 {
  font-size: 1.5rem;
  text-transform: capitalize;
}
.card__footer {
  display: flex;
  padding: 1rem;
  margin-top: auto;
}
.user {
  display: flex;
  gap: 0.5rem;
}
.user__image {
  border-radius: 50%;
  height: 50px;
}
.user__info > small {
  color: #666;
}
#crud {
  margin-top: 5px;
  margin-left: 5px;
}
</style>