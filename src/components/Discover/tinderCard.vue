/* eslint-disable */
<template>
  <div class="">
    <Tinder
      ref="tinder"
      key-name="id"
      :queue.sync="queue"
      :offset-y="10"
      @submit="onSubmit"
    >
      <template slot-scope="scope">
        <div
          class="pic"
          :style="{
            'background-image': `url(https://cn.bing.com//th?id=OHR.${scope.data.id}_UHD.jpg&pid=hp&w=720&h=1280&rs=1&c=4&r=0)`,
          }"
        />
      </template>
      <img
        class="like-pointer"
        slot="like"
        src="@/assets/Swipe_Stamps/Ken.png"
      />
      <img
        class="nope-pointer"
        slot="nope"
        src="@/assets/Swipe_Stamps/Lo.png"
      />
      <img
        class="super-pointer"
        slot="super"
        src="@/assets/Swipe_Stamps/Superfancy.png"
      />
      <img
        class="rewind-pointer"
        slot="rewind"
        src="@/assets/Swipe_Stamps/Superfancy.png"
      />
    </Tinder>
    <div class="btns">
      <b-button @click="decide('rewind')">Rewind</b-button>
      <b-button @click="decide('nope')">nope</b-button>
      <b-button @click="decide('super')">super</b-button>
      <b-button @click="decide('like')">like</b-button>
      <b-button @click="decide('help')">help</b-button>
    </div>
  </div>
</template>

<script>
import Tinder from "vue-tinder";

export default {
  name: "tinderCard",
  components: { Tinder },
  data: () => ({
    queue: [],
    offset: 0,
    history: [],
    peoples: [
      {
        id: "1",
        location: "GreenBoro,NY",
        geolocation: "81 Miles away",
        profileName: "Alexendria Lawson",
        govenrmentName: "alexa lawson",
        email: "alexa@gmail.com",
        birthday: "1996-12-02",
        height: {
          feet: "",
          inches: "",
        },
        profileImages: [],
        livingSituation: "Live Alone",
        doYouHaveChildren: "No",
        doYouWantMoreChildren: "No",
        iAm: "women",
        seeking: "man",
        bodyType: "Slim",
        maritalStatus: "Never Married",
        aboutMe: "Im a good looking women",
        doYouDrink: "No",
        doYouSmoke: "No",
        employmentStatus: "",
        willingToRelocate: "Not Willing To Relocate",
        relationshipIAmSeeking: "Friendship",
        havePets: "Cats",
        havePetsOthers: "",
        howOftenDoYouExercise: "I Exercise 1-2 Times A Week",
        iBelieveIAM: "I am a diaspora isrealite",
        maritalBeliefSystem: "Monogamy",
        spiritualValue: "non-messianic",
        spiritualBackground: "i did not belived in anything",
        studyHabits: "None",
        studyBible: "None",
        anyAffiliation: "No- I Study Alone",
        isrealitePracticeKeeping: [],
        kingdomGifts: [],
        passions: [],
        thumbnail:
          "https://images.unsplash.com/photo-1573497019418-b400bb3ab074?ixlib=rb-1.2.1&ixid=MnwxMjA3fDB8MHxzZWFyY2h8Mnx8YWZyaWNhbiUyMGFtZXJpY2FufGVufDB8MXwwfHw%3D&auto=format&fit=crop&w=500&q=60",
        subscription_type: "premium",
      },
      {
        id: "2",
        location: "GreenBoro,NY",
        geolocation: "81 Miles away",
        profileName: "Stephenie",
        govenrmentName: "stephenie",
        email: "stephenie@gmail.com",
        birthday: "1996-12-02",
        height: {
          feet: "",
          inches: "",
        },
        profileImages: [],
        livingSituation: "Live Alone",
        doYouHaveChildren: "No",
        doYouWantMoreChildren: "No",
        iAm: "women",
        seeking: "man",
        bodyType: "Slim",
        maritalStatus: "Never Married",
        aboutMe: "Im a good looking women",
        doYouDrink: "No",
        doYouSmoke: "No",
        employmentStatus: "",
        willingToRelocate: "Not Willing To Relocate",
        relationshipIAmSeeking: "Friendship",
        havePets: "Cats",
        havePetsOthers: "",
        howOftenDoYouExercise: "I Exercise 1-2 Times A Week",
        iBelieveIAM: "I am a diaspora isrealite",
        maritalBeliefSystem: "Monogamy",
        spiritualValue: "non-messianic",
        spiritualBackground: "i did not belived in anything",
        studyHabits: "None",
        studyBible: "None",
        anyAffiliation: "No- I Study Alone",
        isrealitePracticeKeeping: [],
        kingdomGifts: [],
        passions: [],
        thumbnail:
          "https://images.unsplash.com/photo-1589156191108-c762ff4b96ab?ixlib=rb-1.2.1&ixid=MnwxMjA3fDB8MHxzZWFyY2h8NHx8YWZyaWNhbiUyMGFtZXJpY2FufGVufDB8MXwwfHw%3D&auto=format&fit=crop&w=500&q=60",
        subscription_type: "premium",
      },
      {
        id: "3",
        location: "GreenBoro,NY",
        geolocation: "81 Miles away",
        profileName: "Stephenie",
        govenrmentName: "stephenie",
        email: "stephenie@gmail.com",
        birthday: "1996-12-02",
        height: {
          feet: "",
          inches: "",
        },
        profileImages: [],
        livingSituation: "Live Alone",
        doYouHaveChildren: "No",
        doYouWantMoreChildren: "No",
        iAm: "women",
        seeking: "man",
        bodyType: "Slim",
        maritalStatus: "Never Married",
        aboutMe: "Im a good looking women",
        doYouDrink: "No",
        doYouSmoke: "No",
        employmentStatus: "",
        willingToRelocate: "Not Willing To Relocate",
        relationshipIAmSeeking: "Friendship",
        havePets: "Cats",
        havePetsOthers: "",
        howOftenDoYouExercise: "I Exercise 1-2 Times A Week",
        iBelieveIAM: "I am a diaspora isrealite",
        maritalBeliefSystem: "Monogamy",
        spiritualValue: "non-messianic",
        spiritualBackground: "i did not belived in anything",
        studyHabits: "None",
        studyBible: "None",
        anyAffiliation: "No- I Study Alone",
        isrealitePracticeKeeping: [],
        kingdomGifts: [],
        passions: [],
        thumbnail:
          "https://images.unsplash.com/photo-1589156191108-c762ff4b96ab?ixlib=rb-1.2.1&ixid=MnwxMjA3fDB8MHxzZWFyY2h8NHx8YWZyaWNhbiUyMGFtZXJpY2FufGVufDB8MXwwfHw%3D&auto=format&fit=crop&w=500&q=60",
        subscription_type: "premium",
      },
      {
        id: "4",
        location: "GreenBoro,NY",
        geolocation: "81 Miles away",
        profileName: "Stephenie",
        govenrmentName: "stephenie",
        email: "stephenie@gmail.com",
        birthday: "1996-12-02",
        height: {
          feet: "",
          inches: "",
        },
        profileImages: [],
        livingSituation: "Live Alone",
        doYouHaveChildren: "No",
        doYouWantMoreChildren: "No",
        iAm: "women",
        seeking: "man",
        bodyType: "Slim",
        maritalStatus: "Never Married",
        aboutMe: "Im a good looking women",
        doYouDrink: "No",
        doYouSmoke: "No",
        employmentStatus: "",
        willingToRelocate: "Not Willing To Relocate",
        relationshipIAmSeeking: "Friendship",
        havePets: "Cats",
        havePetsOthers: "",
        howOftenDoYouExercise: "I Exercise 1-2 Times A Week",
        iBelieveIAM: "I am a diaspora isrealite",
        maritalBeliefSystem: "Monogamy",
        spiritualValue: "non-messianic",
        spiritualBackground: "i did not belived in anything",
        studyHabits: "None",
        studyBible: "None",
        anyAffiliation: "No- I Study Alone",
        isrealitePracticeKeeping: [],
        kingdomGifts: [],
        passions: [],
        thumbnail:
          "https://images.unsplash.com/photo-1589156191108-c762ff4b96ab?ixlib=rb-1.2.1&ixid=MnwxMjA3fDB8MHxzZWFyY2h8NHx8YWZyaWNhbiUyMGFtZXJpY2FufGVufDB8MXwwfHw%3D&auto=format&fit=crop&w=500&q=60",
        subscription_type: "premium",
      },
      {
        id: "5",
        location: "GreenBoro,NY",
        geolocation: "81 Miles away",
        profileName: "Stephenie",
        govenrmentName: "stephenie",
        email: "stephenie@gmail.com",
        birthday: "1996-12-02",
        height: {
          feet: "",
          inches: "",
        },
        profileImages: [],
        livingSituation: "Live Alone",
        doYouHaveChildren: "No",
        doYouWantMoreChildren: "No",
        iAm: "women",
        seeking: "man",
        bodyType: "Slim",
        maritalStatus: "Never Married",
        aboutMe: "Im a good looking women",
        doYouDrink: "No",
        doYouSmoke: "No",
        employmentStatus: "",
        willingToRelocate: "Not Willing To Relocate",
        relationshipIAmSeeking: "Friendship",
        havePets: "Cats",
        havePetsOthers: "",
        howOftenDoYouExercise: "I Exercise 1-2 Times A Week",
        iBelieveIAM: "I am a diaspora isrealite",
        maritalBeliefSystem: "Monogamy",
        spiritualValue: "non-messianic",
        spiritualBackground: "i did not belived in anything",
        studyHabits: "None",
        studyBible: "None",
        anyAffiliation: "No- I Study Alone",
        isrealitePracticeKeeping: [],
        kingdomGifts: [],
        passions: [],
        thumbnail:
          "https://images.unsplash.com/photo-1589156191108-c762ff4b96ab?ixlib=rb-1.2.1&ixid=MnwxMjA3fDB8MHxzZWFyY2h8NHx8YWZyaWNhbiUyMGFtZXJpY2FufGVufDB8MXwwfHw%3D&auto=format&fit=crop&w=500&q=60",
        subscription_type: "premium",
      },
    ],
  }),
  created() {
    this.mock();
  },
  methods: {
    mock(count = 5, append = true) {
      const list = [];
      let length = this.peoples.length;
      for (let i = 0; i < count; i++) {
        if (this.offset < length) {
          let current = this.peoples[this.offset];
          list.push(current);
          this.offset++;
        } else {
          this.offset = 0;
        }
      }
      if (append) {
        this.queue = this.queue.concat(list);
      } else {
        this.queue.unshift(...list);
      }
    },
    onSubmit({ item }) {
      if (this.queue.length < 3) {
        this.mock();
      }
      this.history.push(item);
    },
    async decide(choice) {
      if (choice === "rewind") {
        if (this.history.length) {
          this.$refs.tinder.rewind([this.history.pop()]);
        }
      } else if (choice === "help") {
        window.open("https://shanlh.github.io/vue-tinder");
      } else {
        this.$refs.tinder.decide(choice);
      }
    },
  },
};
</script>

<style>
html,
body {
  height: 100%;
}

body {
  margin: 0;
  background-color: #20262e;
  overflow: hidden;
}

#app .vue-tinder {
  position: absolute;
  z-index: 1;
  left: 0;
  right: 0;
  top: 23px;
  margin: auto;
  width: calc(100% - 20px);
  height: calc(100% - 23px - 65px - 47px - 16px);
  min-width: 300px;
  max-width: 355px;
}

.nope-pointer,
.like-pointer {
  position: absolute;
  z-index: 1;
  top: 20px;
  width: 64px;
  height: 64px;
}

.nope-pointer {
  right: 10px;
}

.like-pointer {
  left: 10px;
}

.super-pointer {
  position: absolute;
  z-index: 1;
  bottom: 80px;
  left: 0;
  right: 0;
  margin: auto;
  width: 112px;
  height: 78px;
}

.rewind-pointer {
  position: absolute;
  z-index: 1;
  top: 20px;
  right: 10px;
  width: 112px;
  height: 78px;
}

.pic {
  width: 100%;
  height: 100%;
  background-size: cover;
  background-position: center;
}

.btns {
  position: absolute;
  left: 0;
  right: 0;
  bottom: 30px;
  margin: auto;
  height: 65px;
  display: flex;
  align-items: center;
  justify-content: center;
  min-width: 300px;
  max-width: 355px;
}

.btns img {
  margin-right: 12px;
  box-shadow: 0 4px 9px rgba(0, 0, 0, 0.15);
  border-radius: 50%;
  cursor: pointer;
  -webkit-tap-highlight-color: transparent;
}

.btns img:nth-child(2n + 1) {
  width: 53px;
}

.btns img:nth-child(2n) {
  width: 65px;
}

.btns img:nth-last-child(1) {
  margin-right: 0;
}
</style>