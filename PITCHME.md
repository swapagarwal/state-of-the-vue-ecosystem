---?color=#020203
@title[Introduction]

@transition[none]

@snap[west]
![Vue.js](vuejs.gif)
@snapend

@snap[east]
@size[2em](STATE @color[#e49436](OF) THE<br>@color[#e49436](VUE) ECO@color[#e49436](SYSTEM))
<br><br><br>
@fa[bolt] A look at the current state of Vue.js @fa[bolt]
@snapend

Note:
Hello everyone! Woah, that's a lot of people.

---?image=excited.jpg&size=auto 80%

Note: I'm super excited to be at India's first large-scale Vue conference. We've been pushing to make this happen for quite some time now, be it getting the word out, getting talk proposals, and finally getting you, a houseful of Vue lovers from different parts of the country. So here we are! Let's take a look at the current state of the Vue ecosystem, its community, and some of the recent technical developments. Sit back, relax, and enjoy the View!

---

### A Brief History of Vue

<br>
![Evan You](evan.png)

Note: Vue was created by Evan You after working for Google using AngularJS in a number of projects.

---

"I figured, what if I could just extract the part that I really liked about Angular and build something really lightweight." - Evan You

Note: In his own words, <q>I figured, what if I could just extract the part that I really liked about Angular and build something really lightweight.</q>

---?image=born.jpg&size=auto 80%

Note: And voila, Vue was born.
So Vue is a javascript framework, yes! It's also progressive in nature.
If you're building user interfaces, Vue is a great choice. But don't take our word for it, just go ahead and give it a try. By design, it's easy to pick up and integrate in your existing project. This is in contrast to other monolithic frameworks where you'd typically have to do a full migration. As we'll see in the upcoming talks today, Vue is not just suited for quick-prototyping; it's also perfectly capable of powering large-scale applications as well.

---

### The Buzz Around Vue.js

@ul
- Most Starred JS Framework on GitHub (mid 2018)
- 2nd Most Starred Project on GitHub (early 2019)
@ulend

Note: So, what's the buzz around Vue.js, anyway?
In mid 2018, Vue became the most starred javascript framework on GitHub. Earlier this year, Vue became the second most starred project on GitHub, across all languages (only behind freeCodeCamp)!

---?image=github.png&size=auto 80%

Note: Booyah!
Now I'm not saying that more GitHub stars equals more usage; just that Vue is no longer a new kid on the block and is definitely worth checking out!

---

### Adoption

@ul
- 1,044,987 weekly downloads on NPM
- 973,343 weekly active devtools users
@ulend

Note: Let's see some of the adoption numbers. Vue has over a million weekly downloads on NPM.
Not only that, it has more than 900,000 weekly active devtools users. Devtools is a browser extension to help in debugging, so this number represents the large group of people who are part of the Vue developer community. From my point of view, this metric is more important than the first one. The NPM downloads include a variety of use-cases like that of automated CI builds, downloads for mirroring purposes, and robots that download every package for analysis. However, devtools provides a leading indicator of what's going to come. These 900,000 users are using Vue in their day-to-day work and a significant number of them are going to write more of their future applications in Vue.

---?image=jsdelivr.png&size=auto 80%

@snap[north]
jsDelivr CDN
@snapend

Note: These are the number of hits on the jsDelivr CDN. If you see the 10th place, Vue got over 900 million hits in the last month. That's more than 30 million hits a day. And that's pretty huge! This number is quite high as compared to NPM downloads because Vue provides a drop-in solution. You could just add the CDN file in a script tag and you're ready to use the power of Vue!
Also, note the jQuery and Bootstrap numbers here, at the 7th and 8th places. That's quite close, don't you think?

---?image=numbers.jpg&size=auto 80%

Note: Enough of numbers now!
Let's move onto something real.

---

### Who uses Vue?

@ul
- Laravel
- GitLab
- Behance
- Apple
- Todoist
- Grammarly
- Alibaba
- Netflix
- ... and many more!
@ulend

Note: Who uses Vue? For starters, Laravel! It's the one who kickstarted Vue's adoption. Then we have GitLab, who was again one of the early adopters of Vue. Behance uses Vue. Apple is using Vue. And the list goes on and on!

---

### Who's using Vue.js in India?

@ul
- Ola
- YourStory
- Zoomcar
- The Souled Store
- Kite by Zerodha
- Voicezen
- Sminq
- KarixIO
- ... and many more!
@ulend

Note: Now this one is a frequently asked question, is anyone using Vue in India? Yes, Vue has started seeing adoption in India as well. Some of the companies using Vue are: Ola, YourStory, Zoomcar, The Souled Store, and many more... The point I'm trying to make here is that, Vue is now already being used by your peers. This makes the case for using Vue in your organization a lot easier.

---

### Community

@ul
- Bangalore (900+ members, 2+ years old, blr.vue.community)
- Hyderabad
- Delhi
- Pune
@ulend

Note: But does it have an active community? I'm proud to say that Bangalore's Vue community is now 2 years old, with over 900 members. You can find the meetup link at blr.vue.community. Let's see if we can hit the 1000-member mark by the end of today. We host regular monthly meetups covering a variety of topics. This means that if you face any problem in your day-to-day development, you have people you can reach out to for help. Other cities like Hyderabad, Delhi, and Pune are following suit and have growing communities. The future looks bright! Let's move on to the technical side.

---?image=macross.jpg&size=auto 80%

Note: "Macross" is the codename of the latest release of Vue which is version 2.6
There's an interesting naming convention of the releases; every big release is named after an anime with the next letter of the alphabet. So we've had a ghost in the shell and dragonball as well! You're welcome to place a bet on what the next one might be.

---

### Latest Release: Vue 2.6 "Macross"

@ul
- New slot syntax
- Better async error handling
- Better compiler error messages
- Built-in data prefetch support during SSR
@ulend

Note: Let's see what it brings. One of the most important things that was released in Vue 2.6 is the new slot syntax. We had an RFC for it, and we'll talk more about the details in a bit.
It also comes with an improved asynchronous error handling, so if you use async functions in your lifecycle hooks, the errors during those async processes will actually be captured by Vue's error handlers now. You'll be able to easily handle these errors and send it to your error monitoring services.
This release also improves compiler error messages so now if you make a syntax error in your template and the complier complains, you actually get a code-frame pointing to exactly where you made the mistake. A point worth highlighting is that this feature was contributed by a community member.
Finally, we have built-in data prefetch support during server-side rendering. This is pretty important for all the server-side rendering solutions because up until now, if you try to fetch data on the server, it's tied to your routing system. When you visit a route, you have to place your data fetching logic right in the top-level route component or in the route-specific component else it will be skipped. This places an unnecessary restriction on where your data fetching logic can be placed at. In 2.6, Vue gives you the ability to place your logic anywhere down your component tree. And this greatly simplifies the implementations for higher-order solutions for server-side rendering. Like Nuxt will be able to leverage this to greatly simplify its async data implementation and remove some restrictions. Overall, it will result in a better development experience for server-side rendering apps.

---

### RFCs?

@ul
- Framework for proposing substantial changes
- https://github.com/vuejs/rfcs/
@ulend

Note: Vue has a RFC, or a Request for Comments, process set in place. By the way, this is a great way to get involved in the Vue community. So you can go visit this link on GitHub and propose ideas on how to improve Vue. You can also participate in the ongoing discussions on the open proposals. This makes things open, in the sense that you have visibility of what features are in the pipeline. And it provides an opportunity for someone to point an edge-case in case it was neglected by the core-team. All breaking changes go through RFCs. Let's take a look at some of them:

---

### RFC: New Slot Syntax

@ul
- More clear syntax for default scoped slots
- More consistent and explicit when using named slots
@ulend

Note: Let's see how the unification looks like using some examples.

---

### Default slot with text

```html
<foo><!-- old -->
  <template slot-scope="{ msg }">
    {{ msg }}
  </template>
</foo>

<foo v-slot="{ msg }"><!-- new -->
  {{ msg }}
</foo>
```

---

### Default slot with element

```html
<foo><!-- old -->
  <div slot-scope="{ msg }">
    {{ msg }}
  </div>
</foo>

<foo v-slot="{ msg }"><!-- new -->
  <div>
    {{ msg }}
  </div>
</foo>
```

---

### Named slots

```html
<foo><!-- old -->
  <div slot="one" slot-scope="{ msg }">
    element slot: {{ msg }}
  </div>
</foo>

<foo><!-- new -->
  <template v-slot:one="{ msg }">
    <div>
      element slot: {{ msg }}
    </div>
  </template>
</foo>
```

---?image=darkest.jpg&size=auto 80%

Note: Let's move on to a bit of a controversial RFC, which was making headlines recently. Some even called it Vue's Darkest Day. Let's see what happened.

---

```html
<template>
  <div>
    Count is {{ count }}, count * 2 is {{ double }}
    <button @click="increment">+</button>
  </div>
</template>
```

---

```html
<script>
export default {
  data() {
    return { count: 0 }
  },
  methods: {
    increment() { this.count++ }
  },
  computed: {
    double() { return this.count * 2 }
  }
}
</script>
```

---

```html
<script>
import { value, computed } from 'vue'

export default {
  setup() {
    const count = value(0)
    const double = computed(() => count.value * 2)
    const increment = () => { count.value++ }
    return {
      count,
      double,
      increment
    }
  }
}
</script>
```

Note: So, the initial reaction (including mine) was that this is quite complicated compared to the current syntax, defeating the whole point of Vue being simplistic. All the time people had spent learning Vue had been wasted given everything was about to change.

---

### RFC: Function-based Component API

@ul
- Purely additive to 2.x and doesn't break anything
- No rewrite required if you don't want to
- No plan of deprecating the Object API; it stays for the foreseeable future
@ulend

Note: The best thing about RFCs is that they are not set in stone. It's an invitation to a discussion. And there was a long discussion on this. And modifications were made.

---

### Revised RFC: Composition API

@ul
- Logic Reuse
- Better Type Inference
@ulend

Note: A new revised RFC was opened this month. It makes things simpler while retaining the benefits of Logic Reuse and Better Type Inference.

---

```html
<script>
import { value, computed } from 'vue'

export default {
  setup() {
    const count = value(0)
    const double = computed(() => count.value * 2)

    const increment = () => { count.value++ }

    return { count, double, increment }
  }
}
</script>
```

Note: This is the RFC that was closed.

---

```html
<script>
import { reactive, computed } from 'vue'

export default {
  setup() {
    const state = reactive({
      count: 0,
      double: computed(() => state.count * 2)
    })

    function increment() { state.count++ }

    return { state, increment }
  }
}
</script>
```

Note: Here's a new RFC that was opened this month. To emphasize, this is in open state and you can join the discussion on GitHub.

---?image=mobile.jpg&size=auto 80%

Note: Everyone needs a mobile app nowadays!

---

### State of Mobile Apps

@ul
- NativeScript, Weex
- Quasar, Ionic 4, Onsen UI
@ulend

Note: For building mobile apps, we already have solutions like NativeScript Vue and Weex. We also have mature Cordova-based solutions like Quasar, Ionic 4, and Onsen UI. Quasar released a 1.0 version earlier this year; it's really impressive.

---?image=ssr.jpg&size=auto 80%

Note: Server-side rendering has been on the rise in recent years and aptly so because of the benefits it provides.

---

### State of SSR

@ul
- Nuxt.js
- prerender-spa-plugin
@ulend

Note: Better SEO, as search-engine crawlers directly see the fully rendered page and faster time-to-content, especially on slow internet or slow devices. The Vue ecosystem is sorted on SSR, Nuxt and the prerender-spa-plugin are the most popular choices for achieving this.

---?image=rent.png&size=auto 80%

Note: Coming to sustainability, as GitHub stars don't pay the bills.

---

### Sustainability

@ul
- Patreon
- OpenCollective
@ulend

Note: So, a major difference which makes Vue stand out is that it does not have any corporate backing. The challenge that comes with this is that of sustainability, how do we get people to continue working on this, while making sure the quality is not compromised?
Evan has a Patreon to fund his full-time work on Vue. There is also an OpenCollective, which is backed by the community which funds the work by other core team members. I'd say right now, it's in good shape.

---

### Takeaways

@ul
- Popular
- Active Community
- Performant
- Flexible
- Mobile-Ready
- Here to Stay!
@ulend

Note: To summarize, Vue is getting more popular day-by-day and has started gaining adoption. People around you are already using Vue or learning Vue. The latest release of 2.6 has brought some performance improvements as well. It's flexible, in the sense that it doesn't force you to use any particular template-syntax or TypeScript. Heck, you can even use Pug and Stylus if you don't like closing HTML tags. The mobile ecosystem is quite mature now and ready to take on your requirements. Plus it's sustainable, so it's here to stay for a long time.

---?image=vue3.jpg&size=auto 80%

Note: Aaand Vue 3 is coming! Despite what you may have heard, it doesn't force you to use TypeScript. It's your choice, as developer experience has always been of utmost importance to Vue's principles. Today's closing talk will go into more details about it so stay tuned!

---

### Have a @color[#42b883](Vue)tiful Day!

<br>
![](avatar.png)
<br>
@SwapAgarwal
(<a href="https://swapnil.net/" target="_blank" rel="noopener noreferrer">swapnil.net</a>)

Note: And that's all from my side. My name is Swapnil and you can find me at swapnil.net
Thanks everyone for being here and I hope you Have a Vuetiful Day!
