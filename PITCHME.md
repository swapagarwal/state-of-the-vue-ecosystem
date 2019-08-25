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
Hello everyone! I'm super excited to be here, as we've got a houseful of Vue lovers here today from different parts of the country. If someone had told me that we'll be having a Vue conference a year back, I'd not have believed it. Yet, here we are! Let's take a look at the current state of the Vue ecosystem and some of its recent developments, in the community as well as technical aspects. Sit back, relax, and enjoy the View!

---

### A Brief History of Vue

<br>
![Evan You](evan.png)

Note: Vue was created by Evan You after working for Google using AngularJS in a number of projects.

---

"I figured, what if I could just extract the part that I really liked about Angular and build something really lightweight." - Evan You

Note: In his own words, <q>I figured, what if I could just extract the part that I really liked about Angular and build something really lightweight.</q> And voila, Vue was born.
So Vue is a javascript framework, yes! It's also progressive in nature.
If you're building user interfaces, Vue is a great choice. But don't take our word for it, just go ahead and give it a try. By design, it's easy to pick up and integrate in your existing project. This is in contrast to other monolithic frameworks where you'd typically have to do a full migration. As we'll see in the upcoming talks today, Vue is not just suited for quick-prototyping; it's also perfectly capable of powering large-scale applications as well.

---

### The Buzz Around Vue.js

@ul
- Most Starred JS Framework on GitHub (mid 2018)
- 2nd Most Starrted Project on GitHub (early 2019)
@ulend

Note: So, what's the buzz around Vue.js, anyway?
In mid 2018, Vue became the most starred javascript framework on GitHub. Earlier this year, Vue became the second most starred project on GitHub (only behind freeCodeCamp)! Now I'm not saying that more GitHub stars equals more usage; just that Vue is no longer a new kid on the block and is definitely worth checking out!

---

### Adoption

@ul
- 1,044,987 weekly downloads on NPM
- 973,343 weekly active devtools users
@ulend

Note: Let's see some of the adoption numbers. Vue has over a million weekly downloads on NPM.
Not only that, it has more than 900,000 weekly active devtools users. Devtools is a browser extension to help in debugging, so this number represents the large group of people who are part of the Vue developer community. From my point of view, this metric is more important than the first one. The NPM downloads include a variety of use-cases like that of automated CI builds, downloads for mirroring purposes, and robots that download every package for analysis. However, devtools provides a leading indicator of what's going to come. These 900,000 users are using Vue in their day-to-day work and a significant number of them are going to write more of their future applications in Vue.

---?image=jsDelivr.png&size=auto 80%

@snap[north]
jsDelivr CDN
@snapend

Note: These are the number of hits on the jsDelivr CDN. Vue got over 900 million hits in the last month. That's more than 30 million hits a day. And that's pretty huge! This number is quite high as compared to NPM downloads because Vue provides a drop-in solution. You could just add the CDN file in a script tag and you're ready to use the power of Vue!
Also, note the jQuery and Bootstrap numbers here. That's quite close, don't you think?

---

### Companies using Vue.js in India

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

Note: This one is a frequently asked question, is anyone using Vue? Yes, Vue has started seeing adoption in India as well. Some of the companies using Vue are: Ola, YourStory, Zoomcar, The Souled Store, and many more... Vue is now already being used by your peers. This makes the case for using Vue in your organization a lot easier.

---

### Community

@ul
- Bangalore (900+ members, 2+ years old, blr.vue.community)
- Hyderabad
- Delhi
- Pune
@ulend

Note: But does it have an active community? I'm proud to say that Bangalore's Vue community is now 2 years old, with over 900 members. You can find the meetup link at blr.vue.community. Let's see if we can hit the 1000-member mark by the end of today. We host regular monthly meetups covering a variety of topics. This means that if you face any problem in your day-to-day development, you have people you can reach out to for help. Communities in other cities like Hyderabad, Delhi, and Pune are also growing day-by-day. The future looks very bright!

---

### Latest Release: Vue 2.6 "Macross"

@ul
- New slot syntax
- Better async error handling
- Better compiler error messages
- Built-in data prefetch support during SSR
@ulend

Note: Coming over to the technical side, the latest release was Vue 2.6, codename "Macross". There's an interesting naming convention of the releases; every big release is named after an anime with the next letter of the alphabet. So we've had a ghost in the shell and dragonball as well! You're welcome to place a bet on what the next one might be.
One of the most important things that was released in Vue 2.6 is the new slot syntax. We had an RFC for it, and we'll talk more about the details in a bit.
It also comes with an improved asynchronous error handling, so if you use async functions in your lifecycle hooks, the errors during those async processes will actually be captured by Vue's error handlers now. You'll be able to easily handle these errors and send it to your error monitoring services.
This release also improves compiler error messages so now if you make a syntax error in your template and the complier complains, you actually get a code-frame pointing to exactly where you made the mistake. A point worth highlighting is that this feature was contributed by a community member.
Finally, we have built-in data prefetch support during server-side rendering. This is pretty important for all the server-side rendering solutions because up until now, if you try to fetch data on the server, it's tied to your routing system. When you visit a route, you have to place your data fetching logic right in the top-level route component or in the route-specific component else it will be skipped. This places an unnecessary restriction on where your data fetching logic can be placed at. In 2.6, Vue gives you the ability to place your logic anywhere down your component tree. And this greatly simplifies the implementations for higher-order solutions for server-side rendering. Overall, it will result in a better development experience for server-side rendering apps.

---

### TypeScript

@ul
- Vue's internal implementation moving to TS
- Doesn’t affect non-TS experience
@ulend

Note: TypeScript has really gained some momentum recently and you might have heard that Vue is moving to TypeScript. To clear things here, only the internal implementation is being moved to TypeScript and everything else remains the same.
Being TypeScript-friendly doesn't affect non-TS users' experience. If you are not using TypeScript yet or don't plan to use it, we respect that and you can continue to use Vue as you do today. There's absolutely no need to worry about anything! The API is gonna work the same with or without TypeScript.

---

### RFCs?

@ul
- https://github.com/vuejs/rfcs/
@ulend

Note: Vue has a RFC, or a Request for Comments, process set in place. By the way, this is a great way to get involved in the Vue community. So you can go visit this link on GitHub, propose a new change, and participate in the ongoing discussions on the open proposals. This makes things open, in the sense that you have visibility of what features are in the pipeline. And it provides an opportunity for someone to point an edge-case in case it was neglected by the core-team. All breaking changes go through RFCs. Let's take a look at some of them:

---

### RFC: Slot-based syntax

```html
<!-- default slot -->
<foo v-slot="{ msg }">
  {{ msg }}
</foo>
```

```html
<!-- named slot -->
<foo>
  <template v-slot:one="{ msg }">
    {{ msg }}
  </template>
</foo>
```

---

### RFC: Function-based Component API

---

### RFC: Composition API

---

### State of Mobile Apps

@ul
- NativeScript, Weex
- Quasar, Ionic 4, Onsen UI
@ulend

Note: For building mobile apps, we already have solutions like NativeScript Vue and Weex. We also have mature Cordova-based solutions like Quasar, Ionic 4, and Onsen UI. Quasar released a 1.0 version earlier this year; it's really impressive.

---

### State of SSR

@ul
- Nuxt.js
- prerender-spa-plugin
@ulend

Note: Server-side rendering has been on the rise in recent years and aptly so because of the benefits it provides: Better SEO, as search-engine crawlers directly see the fully rendered page and faster time-to-content, especially on slow internet or slow devices. The Vue ecosystem is sorted on SSR, Nuxt and the prerender-spa-plugin are the most popular choices for achieving this.

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

Note: To summarize, Vue is getting more popular day-by-day and has started gaining adoption. People around you are already using Vue or learning Vue. The latest release of 2.6 has brought some performance improvements as well. It's flexible, in the sense that it doesn't force you to use any particular template-syntax or TypeScript. Heck, you can even use Pug and Stylus if you don't like closing HTML tags. The mobile ecosystem is quite mature now and ready to take on your requirements. And it's sustainable, so it's here to stay for a long time.

---

### Have a Vuetiful Day!

<br>
![](avatar.png)
<br>
@SwapAgarwal
(<a href="https://swapnil.net/" target="_blank" rel="noopener noreferrer">swapnil.net</a>)

Note: That's all from my side. My name is Swapnil and you can find me at swapnil.net
Thanks everyone for being here and I hope you Have a Vuetiful Day!
