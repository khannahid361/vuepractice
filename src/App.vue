<template>
  <div>
    <h1>ep 9</h1>
    <h2>{{ greet }}, {{ name }}!</h2>
    <p v-html="channel"></p>
    <p v-html="channel2"></p>
    <h2 v-html="channel"></h2>
    <div v-html="hack"></div>
    <h2 :id="headingId">Binded id</h2>
    <button :disabled="isDisabled">Disabled</button>
    <button :disabled="isActive">Active and Pressable</button>
    <p :class="show1class && myclass">class is active</p>
    <p :class="show1class && secondclass">class is disabled</p>
    <p :class="[pomt, myclass]">Double class</p>
    <p :class="[show1class ? secondclass : myclass, pomt]">Conditional class</p>
    <p
      :class="{
        'text-red': isDisabled,
        'text-green': show2class,
      }"
    >
      Object Conditional class - note the left side class has to be the css
      class
    </p>

    <h2
      :style="{
        color: highlught,
        fontSize: sizeoffont + 'px',
      }"
    >
      Working on inline style binding from data property
    </h2>

    <h2 :style="styleObject">Using Styling Object</h2>
    <h2 :style="[styleObject, specialFont]">Using Multiple Styling Object</h2>

    <h1>Conditional Binding V-if, else, elseif and V-show episode 11</h1>
    <h4 v-if="num === 0">The Number is Zero</h4>
    <h4 v-else-if="num > 0">The Number is Positive</h4>
    <h4 v-else-if="num < 0">The Number is Negative</h4>
    <h4 v-else>Not A Number</h4>
    <template v-if="isDisplay">
      <h4>lol</h4>
      <h4>lo2X</h4>
      <h4>lo553</h4>
    </template>
    <h1>episode 12 Vshow is used for toggling html</h1>
    <h4 v-show="showelements">pq</h4>
    <hr style="border: 1px solid black" />
    <h1>Episode 13 learning for loop</h1>
    <h4 v-for="(list, index) in lists" :key="index">{{ list }}-{{ index }}</h4>
    <h4 v-for="(dick, index) in fullnames" :key="index">
      {{ dick.first }} - {{ dick.last }}
    </h4>
    <div v-for="(actor, index) in actors" :key="index">
      <h3>{{ actor.identity }}</h3>
      <h5 v-for="like in actor.likes" :key="like">{{ like }}</h5>
    </div>
    <p v-for="(item, key, index) in balls" :key="index">
      {{ key }} - {{ item }} - {{ index }}
    </p>
    <hr style="border: 2px solid black" />
    <h1>Episode 15 Conditional List rendering</h1>
    <template v-for="friend in friends" :key="friend">
      <h3 v-if="friend === 'alif'">{{ friend }}</h3>
    </template>
    <hr style="border: 2px solid black" />
    <h1>Episode 16 Event Handling</h1>
    <h5>The Value Of 10, 20, 30 Addition is {{ add(10, 20, 30) }}</h5>
    <h5>The Value Of 5 X 10 = {{ multiplyBy10(5) }}</h5>
    <hr style="border: 2px solid black" />
    <h1>Episode 17 Event Handling</h1>
    <h2>{{ wife }}</h2>
    <button @click="wife = 'Naima'">Change Your wife</button>
    <h2>{{ count }}</h2>
    <button @click="increment(1)">Increment - 1</button>
    <button @click="increment(5)">Increment - 5</button>
    <button @click="decrement(1)">Decrement - 1</button>
    <button @click="decrement(5)">Decrement - 5</button>
    <hr style="border: 2px solid black" />
    <h1>Episode 19 Form Handling part 1</h1>
    <h2>{{ JSON.stringify(formValues, null, 2) }}</h2>
    <form @submit.prevent="submitForm">
      <div>
        <label for="myName">Name</label>
        <input
          type="text"
          name="myName"
          id="myName"
          v-model="formValues.myName"
        />
      </div>
      <div>
        <label for="profile">Profile Summary</label>
        <textarea
          name="profile"
          id="profile"
          v-model="formValues.profileSummary"
        ></textarea>
      </div>
      <div>
        <label for="country">Country</label>
        <select name="country" id="country" v-model="formValues.country">
          <option value="">Please Select</option>
          <option value="India">India</option>
          <option value="Pakistan">Pakistan</option>
          <option value="Bangladesh">Bangladesh</option>
        </select>
      </div>
      <div>
        <label for="job_location">Job Location</label>
        <select
          name="job_location"
          id="job_location"
          multiple
          v-model="formValues.jobLocation"
        >
          <option value="India">India</option>
          <option value="Pakistan">Pakistan</option>
          <option value="Bangladesh">Bangladesh</option>
        </select>
      </div>
      <hr style="border: 2px solid black" />
      <h1>Episode 20 Form handling Part 2</h1>
      <div>
        <input
          type="checkbox"
          name="remote_job"
          id="remote_job"
          v-model="formValues.remoteWork"
        />
        <label for="remote_job">Open To Work</label>
      </div>
      <div>
        <label>My skills checkbox</label>
        <br />
        <input
          type="checkbox"
          value="html"
          id="html"
          v-model="formValues.skills"
        />
        <label for="html">Html</label>
        <input
          type="checkbox"
          value="css"
          id="css"
          v-model="formValues.skills"
        />
        <label for="css">Css</label>
        <input
          type="checkbox"
          value="php"
          id="php"
          v-model="formValues.skills"
        />
        <label for="php">Php</label>
        <input type="checkbox" value="js" id="js" v-model="formValues.skills" />
        <label for="js">Js</label>
      </div>
      <div>
        <label>My Experience</label>
        <br />
        <input
          type="radio"
          value="0-2"
          id="0-2"
          v-model="formValues.yearsOfExperience"
        />
        <label for="0-2">0-2</label>
        <input
          type="radio"
          value="3-5"
          id="3-5"
          v-model="formValues.yearsOfExperience"
        />
        <label for="3-5">3-5</label>
        <input
          type="radio"
          value="6-8"
          id="6-8"
          v-model="formValues.yearsOfExperience"
        />
        <label for="6-8">6-8</label>
        <input
          type="radio"
          value="9-10"
          id="9-10"
          v-model="formValues.yearsOfExperience"
        />
        <label for="9-10">9-10</label>
      </div>
      <hr style="border: 2px solid black" />
      <h1>Episode 21 Modifiers</h1>
      <div>
        <label for="college">College here setting up trimming modifier</label>
        <input
          type="text"
          name=""
          id="college"
          v-model.trim="formValues.college"
        />
      </div>
      <div>
        <label for="age">Age here setting up number modifier</label>
        <input type="number" name="" id="age" v-model.number="formValues.age" />
      </div>
      <div>
        <label for="university">Age here setting up lazy modifier</label>
        <input
          @keyup.enter="submitForm"
          type="text"
          name=""
          id="university"
          v-model.lazy="formValues.university"
        />
      </div>
      <hr style="border: 2px solid black" />
      <h1>Episode 23 Computed Property</h1>
      <p>
        Computed properties are like data properties, except they depend on
        other properties. <br />

        Computed properties are written like methods, but they do not accept any
        input arguments. <br />

        Computed properties are updated automatically when a dependency changes,
        while methods are called on when something happens, like with event
        handling for example. <br />

        Computed properties are used when outputting something that depends on
        something else.
      </p>
      <h2>The Value Of Movie Tickets - {{ getTotal }}</h2>
      <hr style="border: 2px solid black" />
      <h1>Episode 25 Computed Property and filter function</h1>
      <h3 v-for="movie in costlyMovies" :key="movie.id">
        {{ movie.name }} - {{ movie.ticketPrice }}
      </h3>
      <hr style="border: 2px solid black" />
      <h1>Episode 25 Computed Property Setter</h1>
      <h2>{{ fetchName }}</h2>
      <button @click="changeFullName()">Change Name</button>
      <hr style="border: 2px solid black" />
      <h1>Episode 27 Watchers</h1>
      <h2>Current Volume</h2>
      <h4>{{ volume }}</h4>
      <button @click="volume += 5">+5</button>
      <button @click="volume -= 5">-5</button>
      <hr style="border: 2px solid black" />
      <h1>Episode 28 Intermediate and Deep Watcher</h1>
      <input type="text" name="" id="" v-model="show" />
      <input type="text" name="" id="" v-model="showInfo.title" />
      <input type="text" name="" id="" v-model="showInfo.actor" />
      <button @click="showList.push('Superman')">Add Show</button>
      <hr style="border: 2px solid black" />
      <!-- <div>
        <button>Submit</button>
      </div> -->
    </form>
    <GreetUser foodName="Apple" heroName="Batman" />
    <GreetUser foodName="Mango" heroName="Spiderman" />
    <GreetUser foodName="Rice" heroName="SuperMan" />
    <hr style="border: 2px solid black" />
    <SmartTool :foodName="name" :heroName="channel2" />
    <hr style="border: 2px solid black" />
    <h1>
      Ep 31 Prop Types and validation means it will teach me how to define props
      with their types
    </h1>
    <PropValidation title="Vue Practice" :numericalValue="31" />
    <hr style="border: 2px solid black" />
    <h1>
      Ep 32 - Non Prop Attributes defaultly bonds the root div but by
      inheritiing false we can make a element inside the root div of a component
      to apply only on that element
    </h1>
    <NonPropProperty id="hunter" />
    <hr style="border: 2px solid black" />
    <h1>Ep 33 - Provide and Inject</h1>
    <MasterComponent />
    <hr style="border: 2px solid black" />
    <h1>Ep 34 - Component Events</h1>
    <button @click="showPopUp = true">Show Pop Up</button>
    <PopUp v-show="showPopUp" @close="closePopup" />
    <hr style="border: 2px solid black" />
    <h1>Ep 35 - Validating Emitted Events</h1>
    <button @click="showPopUp2 = true">Show Pop Up 2</button>
    <CustomEvent v-show="showPopUp2" @close="closePopup2" />
    <hr style="border: 2px solid black" />
    <h1>Ep 36 - Components and v-model</h1>
    <ComponentVmodel v-model="surName" />
    <h2>{{ surName }}</h2>
    <hr style="border: 2px solid black" />
    <h1>Ep 37 - Slots</h1>
    <CardComponent>
      <h1>I have declared a slot</h1>
    </CardComponent>
    <CardComponent>
      <textarea name="" id="">This is a slot input field</textarea>
    </CardComponent>
    <CardComponent></CardComponent>
    <CardComponent>Slots in Vue.js are a powerful feature that allows you to pass content from a parent component to a child component. They enable you to create reusable and flexible components. Vue provides three types of slots: default slots, named slots, and scoped slots.</CardComponent>
    <hr style="border: 2px solid black" />
    <h1>Ep 38 Named Slot</h1>
    <CardComponent>
      <template v-slot:header>
        <h1 style="color: red;">V-sloat:header - First Sloat Header</h1>
      </template>
      <template v-slot:default>
        <h1 style="color:green">V-sloat:default - First Sloat default / Content</h1>
      </template>
      <template v-slot:footer>
        <h1 style="color:blue">V-sloat:footer - First Sloat footer</h1>
      </template>
    </CardComponent>
    <hr style="border: 2px solid black" />
    <h1>Ep 39 Sloat Props</h1>
    <NameList>
      <template v-slot:default="slotProps">
        {{ slotProps.firstName }} {{ slotProps.lastName }}
      </template>
    </NameList>
    <NameList>
      <template v-slot:default="slotProps">
        {{ slotProps.lastName }} {{ slotProps.firstName }}
      </template>
    </NameList>
    <NameList>
      <template v-slot:default="slotProps">
        {{ slotProps.firstName }}
      </template>
    </NameList>
    <h2 style="color:red"></h2>
    <hr style="border: 2px solid black" />
    <h1>Ep 40 - Component Styles</h1>
    <h4>App Component Text</h4>
    <ChildStyles/>
    <hr style="border: 2px solid black" />
    <h1>Ep 41 - Dynamic Components</h1>
    <button @click="activeTab='TabA'">Tab A</button>
    <button @click="activeTab='TabB'">Tab B</button>
    <button @click="activeTab='TabC'">Tab C</button>
    <TabA v-if="activeTab==='TabA'"></TabA>
    <TabB v-if="activeTab==='TabB'"></TabB>
    <TabC v-if="activeTab==='TabC'"></TabC>
    <h3>I can do it with Dynamic Component watch the app component</h3>
    <h1>EP- 42 - Keeping Dynamic Components Alive</h1>
    <keep-alive>
      <component :is="activeTab"></component>
    </keep-alive>
    <hr style="border: 2px solid black" />
    <h1>Ep 43 - Teleport Component</h1>
    <teleport to='#portalRoot' >
      <PortalRoot></PortalRoot>
    </teleport>
    <hr style="border: 2px solid black" />
    <h1>Ep 45 - HTTP GET Request</h1>
    <PostList/>
    <hr style="border: 2px solid black" />
    <h1>Ep 46 - HTTP POST Request</h1>
    <CreatePost />
    <hr style="border: 2px solid black" />
    <UpdatePost />
    <hr style="border: 2px solid black" />
    <DeletePost />
    <hr style="border: 2px solid black" />
    <h1>Ep  48 - GET Request on Page Load</h1>
    <RequestOnLoad />
    <hr style="border: 2px solid black" />
    <h1>Ep 49 - Template Refs</h1>
    <TemplateRef />
    <hr style="border: 2px solid black" />
    <h1>Ep 50 Reusability with Mixins</h1>
    <ClickCounter />
    <hr style="border: 2px solid black" />
    <HoverCounter />
    <h2 class="text-red">We used mixins here for the purpose of reuseability of same code in Clickcounter and Hovercounter Component</h2>
    <hr style="border: 2px solid black" />
    <h1>Ep 52 - Replacing data with ref</h1>
    <ChangeData />
    <hr style="border: 2px solid black" />
    <h1>Ep 54 - Reactivity and toRefs</h1>
    <DemoOne />
    <hr style="border: 2px solid black" />
    <DemoTwo />
    <hr style="border: 2px solid black" />
    <h1>EP 55 - Replacing methods</h1>
    <ChangeMethod />
    <hr style="border: 2px solid black" />
    <h1>Ep 56 - v-model and Composition API</h1>
    <CompositionVmodel />
    <hr style="border: 2px solid black" />
    <h1 class="text-red">Ep 57 - Replacing Computed Properties</h1>
    <ChangeComputed />
    <hr style="border: 2px solid black" />
    <h1 class="text-red">Ep 58 - Replacing Watchers (Part 1)</h1>
    <ReplaceWatcher />
    <hr style="border: 2px solid black" />
    <h1>Ep 60 - Replacing Provide/Inject</h1>
    <ReplaceProvideInject />
    <hr style="border: 2px solid black" />
    <h1>Ep 62 - Template Refs and Composition API</h1>
    <ReplaceTemplateRefs />
    <hr style="border: 2px solid black" />
    <h1>Ep 63 - Props and Composition API</h1>
    <ManagePerson />
    <hr style="border: 2px solid black" />
    <h1>EP 64 - Custom Events and Composition API</h1>
    <hr style="border: 2px solid black" />
  </div>
</template>

<script>
import GreetUser from "./components/GreetUser.vue";
import SmartTool from "./components/SmartTool.vue";
import PropValidation from "./components/PropValidation.vue";
import NonPropProperty from "./components/NonPropProperty.vue";
import MasterComponent from "./components/MasterComponent.vue";
import PopUp from "./components/PopUp.vue";
import CustomEvent from "./components/CustomEvent.vue";
import ComponentVmodel from "./components/ComponentVmodel.vue";
import CardComponent from "./components/CardComponent.vue";
import NameList from "./components/NameList.vue";
import ChildStyles from "./components/ChildStyles.vue";
import TabA from "./components/TabA.vue";
import TabB from "./components/TabB.vue";
import TabC from "./components/TabC.vue";
import PortalRoot from "./components/PortalRoot.vue";
import PostList from "./components/PostList.vue";
import CreatePost from "./components/CreatePost.vue";
import UpdatePost from "./components/UpdatePost.vue";
import DeletePost from "./components/DeletePost.vue";
import RequestOnLoad from "./components/RequestOnLoad.vue";
import TemplateRef from "./components/TemplateRef.vue";
import ClickCounter from "./components/ClickCounter.vue";
import HoverCounter from "./components/HoverCounter.vue";
import ChangeData from "./components/ChangeData.vue";
import DemoOne from "./components/DemoOne.vue";
import DemoTwo from "./components/DemoTwo.vue";
import ChangeMethod from "./components/ChangeMethod.vue";
import CompositionVmodel from "./components/CompositionVmodel.vue";
import ChangeComputed from "./components/ChangeComputed.vue";
import ReplaceWatcher from "./components/ReplaceWatcher.vue";
import ReplaceProvideInject from "./components/ReplaceProvideInject.vue";
import ReplaceTemplateRefs from "./components/ReplaceTemplateRefs.vue";
import ManagePerson from "./components/ManagePerson.vue";
export default {
  name: "App",
  components: {
    GreetUser,
    SmartTool,
    PropValidation,
    NonPropProperty,
    MasterComponent,
    PopUp,
    CustomEvent,
    ComponentVmodel,
    CardComponent,
    NameList,
    ChildStyles,
    TabA,
    TabB,
    TabC,
    PortalRoot,
    PostList,
    CreatePost,
    UpdatePost,
    DeletePost,
    RequestOnLoad,
    TemplateRef,
    ClickCounter,
    HoverCounter,
    ChangeData,
    DemoOne,
    DemoTwo,
    ChangeMethod,
    CompositionVmodel,
    ChangeComputed,
    ReplaceWatcher,
    ReplaceProvideInject,
    ReplaceTemplateRefs,
    ManagePerson
  },
  data() {
    return {
      activeTab : 'TabA',
      name: "Kamrul",
      greet: "Hello",
      channel: "<b>CodeEvolution</b>",
      channel2: "CodeEvolution",
      hack: `<a href="#" onclick="alert('You have been hacked')">Win A Prize</a>`,
      headingId: "heading",
      isDisabled: true,
      isActive: false,
      myclass: "text-red",
      secondclass: "text-green",
      show1class: true,
      show2class: false,
      pomt: "promoted",
      highlught: "orange",
      sizeoffont: 50,
      styleObject: {
        color: "orange",
        fontSize: "50px",
      },
      specialFont: {
        fontStyle: "italic",
      },
      num: "l",
      isDisplay: true,
      showelements: true,
      lists: ["text", "icon", "font", "lol"],
      fullnames: [
        { first: "a", last: "b" },
        { first: "c", last: "d" },
        { first: "e", last: "f" },
        { first: "g", last: "h" },
        { first: "i", last: "j" },
      ],
      actors: [
        { identity: "A", likes: ["a", "b"] },
        { identity: "B", likes: ["c", "d"] },
        { identity: "C", likes: ["e", "f"] },
        { identity: "D", likes: ["g", "h"] },
        { identity: "E", likes: ["i", "j"] },
      ],
      balls: {
        name: "tennis",
        color: "green",
        bat: "racket",
      },
      friends: ["asad", "hamza", "alif"],
      baseMultiplyer: 10,
      wife: "Nahida",
      count: 0,
      formValues: {
        myName: "",
        profileSummary: "",
        country: "",
        jobLocation: [],
        remoteWork: false,
        skills: [],
        yearsOfExperience: "",
        college: "",
        age: null,
        university: "",
      },
      movies: [
        {
          id: 1,
          name: "Shawshank Redemption",
          ticketPrice: 100,
        },
        {
          id: 2,
          name: "Katalaga",
          ticketPrice: 200,
        },
        {
          id: 3,
          name: "Girlfriend Er Biya",
          ticketPrice: 300,
        },
      ],
      firstName: "Kamrul",
      lastName: "Hasan",
      volume: 0,
      show: "Batman",
      showInfo: {
        title: "",
        actor: "",
      },
      showList: ["Batman", "Kamrul"],
      showPopUp : false,
      showPopUp2 : false,
      surName: ''
    };
  },
  methods: {
    add(a, b, c) {
      return a + b + c;
    },
    multiplyBy10(num) {
      return num * this.baseMultiplyer;
    },
    increment(x) {
      this.count += x;
    },
    decrement(y) {
      this.count -= y;
    },
    submitForm() {
      console.log("form values", this.formValues);
    },
    changeFullName() {
      this.fetchName = "Super Boy";
    },
    closePopup(xValue) {
      this.showPopUp = false;
      console.log('xValue: ' + xValue);
    },
    closePopup2(xValue) {
      this.showPopUp2 = false;
      console.log('xValue: ' + xValue);
    }
  },
  computed: {
    getTotal() {
      return this.movies.reduce(
        (total, curr) => (total = total + curr.ticketPrice),
        0
      );
    },
    costlyMovies() {
      return this.movies.filter((movie) => movie.ticketPrice > 100);
    },
    fetchName: {
      get() {
        return ` ${this.firstName} - ${this.lastName}`;
      },
      set(value) {
        const nam = value.split(" ");
        this.firstName = nam[0];
        this.lastName = nam[1];
      },
    },
  },
  watch: {
    volume(newValue, oldValue) {
      if (newValue > oldValue && newValue === 20) {
        alert("Warning You are not allowed to listen to this high volume");
      }
    },
    show: {
      handler(newValue) {
        console.log(
          `using show as object in the watcher so that we can fetch data calling an api on load with immediate  = ${newValue}`
        );
      },
      immediate: true,
    },
    showInfo: {
      handler(newValue) {
        console.log(
          `calling an api with title  = ${newValue.title} and actor = ${newValue.actor} will not work untill setting it to deep to true`
        );
      },
      deep: true,
    },
    showList: {
      handler(newValue) {
        console.log(
          `${newValue} we have to deep to true to see the value from adding by button`
        );
      },
      deep: true,
    },
  },
  provide: {
    myUserName : 'MD: Sarker Kamrul Hasan'
  }
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

.text-red {
  color: red;
}

.text-green {
  color: rgb(29, 6, 235);
}

.promoted {
  font-style: italic;
}

h4 {
  color: orange;
}
</style>