
Schalk Venter: **Shailen is your audio working?**

Jonathan McAwesome: **Morning!**

Johannes: **Hey everyone. Excited to be here.**

Schalk Venter: **Morning Joh!**

Schalk Venter: **Your dog was going ballistic in the background when you had the video on! :)**

Albert: **Hi All**

Schalk Venter: **Hey Albert**

Elizabeth Meyer: **Hi All too :-)**

Jonathan McAwesome: **Hay all**

Johannes: **😆 I don’t even have a dog Schalk!**

Sazi Mtandabuzo: **Wish meet ups could also be delivered in this format even post covid-19**

Albert: **Yes I can see it perfectly**

Jonathan McAwesome: **15 of 120 #MeetupStats**

Thando Toto: **I’m glad you made online. Joining from Switzerland**

Thando Toto: ***made it**

Schalk Venter: **Nice! Welcome Thando!**

Johannes: **Is this the first online meetup for CT Frontend Devs?**

Schalk Venter: **Yeah, first online.**

Johannes: **Nice!**

Schalk Venter: **I'll keep an eye on the chat and will bug Shailen if he misses any questions posted here.**

Elizabeth Meyer: **Is that the #front-end-dev channel on ZATECH slack?**

Schalk Venter: **Yeah, #front-end-dev**

catonice: **What exactly does "painting" entail?**

Schalk Venter: **It is the actual creating of the UI in the browser.**

Lourens de Villiers: **the visual rendering in the window. When you change padding of an element with JS it triggers a repaint**

Johannes: **Why don’t we have that UI/non-UI thread separation for webpages as standard in the browser yet?**

Schalk Venter: **As far as I'm aware this was just part of it's design initially.**

Schalk Venter: **I think we can post question here as Shailen goes and then he can address all of them once he is done.**

Schalk Venter: **Don't want to interrupt him now. :)**

Johannes: **👍**

Johannes: **Makes sense, thanks Shailen.**

mrkiffie: **Browsers themselves are not single threaded - but the context that the website runs in is single threaded.**

Jonathan McAwesome: **Great slide**

Schalk Venter: **Yeah, loving those animations! :D**

Michael Wiles: **from someone who has done his fair share of gui programming - javascript's approach saves you from many headaches. It's tricky to make sure you don't "capture" the ui when you have multiple threads available.**

Johannes: **@Michael I see… It just seems counterintuitive to me that with all the optimisation browsers are doing out of the box nowadays, and with multithreading with web workers have been around for a decade, that browsers don’t yet automatically ‘optimise’ all the work (painting, JS, etc.) over multiple threads.**

Johannes: **Really interesting presentation so far, thanks Shailen!**

catonice: **This has been really good so far!**

Schalk Venter: **Yeah Shailen is JavaScript Jedi!**

Johannes: **Yup, it’s good for me.**

Lourens de Villiers: **good here**

Jonathan McAwesome: **Haha HOTSEAT**

catonice: **We'll do it LIVE!**

Lourens de Villiers: **Does it break the worker itself or the script it’s importing?**

Schalk Venter: **Lourens can you give a bit more context? Not 100% what you're asking?**

Lourens de Villiers: **Shailen said if the imported script in the worker tries to access the window, it breaks, so…Does it break the worker itself or the script it’s importing? in other words the imported script won’t work.**

Lourens de Villiers: **which I guess could also break the worker afterwards depends how you import it. ignore me**

mrkiffie: **`window` and `document` for example will be `undefined` - so it will fail in the same way when you try to access a property of undefined. Depending on how the code is written, it could mean an isolated failure that gets caught, or it could break it entirely**

Lourens de Villiers: **that explains it thanks!**

Johannes: **If the worker breaks entirely, how will we know about it in the main thread, i.e. if it doesn’t “post” back a message? Is there a way to ‘catch’ the error back in the main window, i.e. will it ‘throw’ the error to the main thread?**

Baadier Sydow: **Thats pretty cool about the threading**

Lourens de Villiers: **Does each worker live on its own thread?**

Schalk Venter: **Johannes you treat it similar to how you would for example with a failing promise/fetch.**

Jonathan McAwesome: **Geeze that's epic**

Johannes: **Ah, I see.**

Schalk Venter: **You can do an `onerror` call.**

Schalk Venter: **I don't think it bubbles up to the main thread though, so you need to explicitly catch it in the main thread.**

mrkiffie: **In the the main thread, you can add an `onerror` handler to the worker instance.**

mrkiffie: 

```js
var worker = new Worker("worker.js");

worker.onerror = function(event){
    throw new Error(event.message + " (" + event.filename + ":" + event.lineno + ")");
};
```

Johannes: **Makes sense.**

Elizabeth Meyer: **That is very cool. Thank you...**

catonice: **Do web workers have a significant impact on hardware performance if lets say the user has small amount of RAM and has all these web workers running?**
I'm curious

Schalk Venter: **Will ask Shailen to look at chat if anyone wants to ask questions here as well.**

mrkiffie: **Web workers can also create other Web workers**

catonice: **@Schalk ye got one there *points up :)**

Baadier Sydow: **Really great question and answer :)**

Lourens de Villiers: **Does each web worker then live on its on thread? (separate from other web workers)**

catonice: **Thanks yes answers it!**

catonice: **Q: Any other good real world examples of web workers?**

Johannes: **Q: Any *bad* examples of web workers, i.e. what they shouldn’t be used for?**

catonice: **hahah XD**
**
Nathan Shepherd: **Are there any "gotchas" for web workers we should watch out for? And are there any best practices that should be followed?**

mrkiffie: **The number of workers that you spin up should ideally be less that the "logical processors" the device has. This can be accessed by `window.navigator.hardwareConcurrency`**

Lourens de Villiers: **Ah thanks mrkiffie, that was kind of where i was going with that question**

Baadier Sydow: **You could push computationally heavy tasks to a serveless function to handle the missing web workers. Still get similar performance but with network overhead.**

Baadier Sydow: **lol**

Baadier Sydow: **in the context of browsers that dont have access to**

Baadier Sydow: **yeah cause the engines are slower on older ones**

catonice: **Q: Any other good and bad real world examples of web workers? Are there any "gotchas" for web workers we should watch out for? And are there any best practices that should be followed? Copying other qs into a big Q**

mrkiffie: **One great example that I've seen utilise web workers is https://squoosh.app/**

catonice: **Thanks!**

Schalk Venter: **https://www.amazon.com/Web-Workers-Multithreaded-Programs-JavaScript/dp/1449322131**

Schalk Venter: **Book I mentioned.**

Johannes: **Yeah, good answer, thanks!**

Thando Toto: **I’m interested, please share those resources.**

catonice: **I'd like the share as well**

Nathan Shepherd: **So in the context of performance and avoiding certain foot guns or potential tech debt.**

Baadier Sydow: **I would be keen to hear that talk Shailen!**

Nathan Shepherd: **Wow, ok - I was wondering about posting objects, good to know about the closure gotcha as well, makes sense.**

Albert: **Q: Hi Shailen. I'm not sure if I heard you correctly. Please can you clarify this point? You said that you can set up a fucnction so that dynamically a web worker runs and closes once the session is closed or when the tab is closed does that apply for the service worker that interact with the network in the back end?**

mrkiffie: **There are some data types that recently got support for being transferred without the json serialisation. Once these have been transferred, you can no longer access them in the originating context. Transferable = ArrayBuffer | MessagePort | ImageBitmap | OffscreenCanvas**

Thando Toto: **Thanks for clarifying that about Vue Shailen.**

catonice: **Thank you for the talk Shailen! I have to head out, thanks everyone for organizing and participating!**

Schalk Venter: **Thanks for joining Catonice!**

Lourens de Villiers: **https://medium.com/@wl1508/webworker-in-tensorflowjs-49a306ed60aa**

Lourens de Villiers: **Tl:dr - TensorFlow.js just got native support for web workers! With web workers, long-running computation will not block the UI.**

Lourens de Villiers: **Good use case for ML in the browser**

Albert: **Thanks Shailen**

shailen: **https://proxx.app/**

mrkiffie: **All communication with the web worker instance happens over the `postMessage` - which is essentially a single channel. So if you're processing multiple items of a similar type, you usually need a way to identify the the return message belongs to A or B or C, etc. For workers that support multiple types of processing, you need the data structure to define what "type" of data/processing it is - both when sending and receiving.**

mrkiffie: **https://www.npmjs.com/package/worker-plugin**

Lourens de Villiers: **Thanks Shailen, it’s been very informative!**

mrkiffie: **Thanks Shailen!**

Michael Wagener: **Thanks Shailen… :)**

Johannes: **Thank you Shailen! This has been great.**

Baadier Sydow: **I've already shared it in my team chat for discussion on Monday :)**

Nathan Shepherd: **Thanks Shailen, Schalk and Justin, and all organisers. Looking forward to the next one.**

Johannes: **Thanks folks!**

mrkiffie: **Cheers!!**
