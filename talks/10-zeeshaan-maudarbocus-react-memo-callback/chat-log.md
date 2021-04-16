Jonathan_faulty_it: **Hay all**

Lea: **Heeeyyyy nice to see you here Luke 👋**

Sky: **</3**

Kiffie Liversage: **https://en.wikipedia.org/wiki/Fabio_Lanzoni**

Lea: **Goals haha**

Jonathan_faulty_it: **Florida man**

Sabir: **Hi y'all**

Jonathan_faulty_it: **Haha sleep is for the week**

Kevin: **Hi 👋**

Jonathan_faulty_it: **Will continue to react**

Kiffie Liversage: **"We ask people to leave..." DRAMATIC PAUSE "...questions in the chat"**

Jonathan_faulty_it: **🤫🤫🤫**

Kiffie Liversage: **👻**

Yeukai Loreen: **I thought it was memoRisation😅 . geez**

Schalk Venter: **Ha!**

Lea: **Saaame, I thought it was a typo at first 😬**

Schalk Venter: **Whenever I pronounce it is just Mem-*mumbles*-ation**

Martin Kruger: **Could you possibly zoom into a tiny bit in the editor please? The text is somewhat distorting**

Martin Kruger: **Thanks**

Schalk Venter: **No worries!**

Jonathan_faulty_it: **Tnx**

Schalk Venter: **Jonathan is viewing it on his Nokia 1cm screen :D**

Jonathan_faulty_it: **False closed captions via telegram 😂**

Schalk Venter: **Haha! I can give you live commentary as it happens**

Schalk Venter: **Do you guys see those yellow lines at the bottom of the screen?**

Schalk Venter: **I think Jonathan drew them (acciddentaly I hope!)**

Yeukai Loreen: **yes**

Schalk Venter: **Donno how to get rid of it :D**

Sabir: **Username checks**

Sky: **I love magic**

Chris Marais: **Very wow**

Lea: **Live coding in front of 30 people like a BOSS 💪**

Schalk Venter: **"That's an old Ninja"**

Schalk Venter: **As someone turning 34 this year 😰**

Sky: **Magic indeed**

Kiffie Liversage: **let ninja = { weapon: "Shuriken" }**

Amo: **geez didn't know you're that old**

Schalk Venter: **:(**

WIkus Schalkwyk: **what is person was instantiated woth "const" and not "let" ?**

Kiffie Liversage: **Why is the `React.memo` HOC behaviour not always applied to child react components?**

WIkus Schalkwyk: **"what if"**

Sky: **I'm assuming it's because the check takes time and you don't always want to run the check**

Schalk Venter: **Kiffie was that correct?**

Kiffie Liversage: **yes**

Kiffie Liversage: **Can memoization result in a memory leak?**

Nathan Shepherd: **Also your heap size will just keep growing if every component is assigned to memory by default.**

musango: **would you say then an ideal is build the component first then see where you can apply memoization to improve performance?**

Sky: **^ 100**

Yeukai Loreen: **can I just use memo on any default export without checking the component**

Kiffie Liversage: **@Nathan Stack: How my clothes are arranged when I get them back from the Laundry. Heap: How my clothes are arranged on the floor after I've worn them.**

Kiffie Liversage: **When should you use `useCallback`?**

Adrian Bunge: **So a standard button would be great for a memo without equality check**

WIkus Schalkwyk: **does it cache the result of the function?**

Kiffie Liversage: **If I create a custom hook - should I use `useCallback` and `useMemo` inside the custom hook?**

musango: **same**

Stuart McCulloch: **Would memo have a negative effect on SEO scores?**

Kiffie Liversage: **Re:SEO I wonder if using `memo` on a component that doesn't take any props would be worse for rehydration speed of a server rendered app.**

Schalk Venter: **@Wikus, yeah `useMemo` caches result of function, whereas `memo` caches the component itself.**

Schalk Venter: **@Stuart, I don't see that it would.**

Kiffie Liversage: **@Wikus: `useCallback` will return a reference to the function that was passed to it on the first render, unless the values in the dependency array change. When the dependencies change, a reference to the new function that was passed in will be returned. `useMemo` will return the result of the function passed in. The function is only evaluated when the dependencies change**

Schalk Venter: **Ah, I see the question was specifically in relation to `useCallback`**

WIkus Schalkwyk: **k  cool, thanks @Kiffie**

Schalk Venter: **Yeah, for a long time I though it memorized the result of the function, but as Kiffie said - it just keeps the referential equality**

Schalk Venter: **So function1 === function2**

Kiffie Liversage: **`useCallback` is basically syntactic sugar for `useMemo(() => () => { console.log('hello'))`**

Schalk Venter: **Kiffie that is pretty neat, never really thought about it that way. :)**

WIkus Schalkwyk: **thanks peeps. have to bounce.**

Stuart McCulloch: **Decreasing initial render… rehydration issues ensue surely?**

Schalk Venter: **Ah, fair point. My frame of reference is JAM Stack, so it shouldn't be a problem there.**

Schalk Venter: **However, I see the point regarding initial running of JS**

Kiffie Liversage: **The first rule of hooks is "install the eslint-plugin-react-hooks plugin". At least it should be... :) https://reactjs.org/docs/hooks-rules.html#eslint-plugin**

Schalk Venter: **I don't know how people use hooks without the ESLint plugin.**

Nathan Shepherd: **How would you go about unit testing memoization?**

Lea: **’tis the law 🙌**

Kiffie Liversage: **NaN**

Schalk Venter: **:D**

Kiffie Liversage: **I never knew about the `<Profiler>` component. This is pretty cool. https://reactjs.org/docs/profiler.html**

Schalk Venter: **Yeah, Profiler is amazing!**

Nathan Shepherd: **Yea, Profiler is definitely something I'm going to be playing around with.**

Sky: **Profiler ftw**

Nathan Shepherd: **Bonus content!**

Kiffie Liversage: **Make it work, make it right, make it fast. -- Kent Beck**

Nathan Shepherd: **Syntax.fm just released a podcast on DevTools. Check it out.**

micasmith: **Very interesting stuff, thanks Zee! Think I’ll join more of these sessions in future. Gotta run though, nice meeting you guys. Cheers :)**

Lea: **I relate more to make it pretty tbh**

Stuart McCulloch: **Same @Lea**

Caitlyn Fowkes: **That was rad Zee :) nice one**

Sabir: **Great talk Zee! Have to sign out now. Cheers y'all**

Nathan Shepherd: **You should if you code split though, right?**

musango: **pretty good example**

Stuart McCulloch: **Thought about code splitting… using ssr so may have to go for loadable**

Duncan: **Thanks for the talk Zeeshaan, and thanks to everyone who made this talk possible. :) Goodbye.**

Nathan Shepherd: **I had one earlier, about unit testing memoization. Any tips or tricks?**

Kiffie Liversage: **Thanks for the talk.**

Nathan Shepherd: **Thanks Zee. Awesome stuff.**

musango: **i find storybook more valuable for more ui heavy component**

Nathan Shepherd: **Where can we find/follow you? Plug it!**

Stuart McCulloch: **Thanks so much - very informative talk.**

Nathan Shepherd: **Really looking forward to that one. How did you land it, Schalk?**

Kiffie Liversage: **Programming Quotes: https://gist.github.com/OnesimusUnbound/3064220**

Lea: **Whoohooo looking forward to that one!**

Sky: **Thanks a lot. I learned about useMemo and Profiler...**

ZeeDawg **😎**

Zeeshaan Maudarbocus: **I Appreciate the feedback guys**

Lea: **Thanks Zee, super interesting one!**

Dylan: **shot Zeeshaan, that was a very cool talk! learned a lot**

Stuart McCulloch: **“Where can we find/follow you? Plug it!” - Nathan**

Nathan Shepherd: **Thanks @Stuart**

Zeeshaan Maudarbocus: **https://www.linkedin.com/in/zeeshaan-maudarbocus/**

Caitlyn Fowkes: **Cheers guys!**

Joseph: **cheers**

Kiffie Liversage: **Cheers!**

Nathan Shepherd: **Cheers guys, thanks again.**

Matt Clarke: **thanks**
