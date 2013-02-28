How many of you have used the course 6 jobs list?
Okay, well, this is the story of how I came to replace it, and what I learned along the way.

I'm going to give you some contextual info about why I undertook this project, then I'll describe my underlying goals, and I'll tell you about the tools I used to achieve them. Then I'll give you a brief demo of the site. Sound good?

Okay, let's get started. So, I'm the webmaster for a student group on campus called StartLabs. We are adamant lovers of startups. Naturally, we're interested in servicing startups around the world while helping out MIT kids. So I took on the task of implementing a Jobs list as a web application at the beginning of this year that was catered towards startups.

A few weeks ago, one of my teammates was having a conversation with Anne Hunter, and suggested that we manage the startup-related postings to the course 6 jobs list. Now, when I set out to make the list, I never anticipated taking on this responsibility. But I thought, hey, why not.

So I've been steadily adding functionality to the jobs list to satisfy 3 these key guiding principles. In my mind, the site needs to be:

- Usable: and by that I mean, designed for the task at hand. I want to be able to see all of the jobs laid out in front of me and explore them visually.
- Feature-rich: email is a nice universal interface, but it's lacking some valuable functionality for sorting and filtering listings.
- Easily-extensible: the truth of the matter is, no matter how many features I add to the site, someone is going to be dissatisfied. So rather than try and appease everyone, I want to give students the tools to build what *they* want. So this means exposing all of the information on the site through a simple API. Also, the site is open source and on Github: anyone can submit pull requests if they want to change the site.

Okay, so that was some context. Now I want to give you a bit of background on the tools I used to make the site.

In 2008, a guy named Rich Hickey released a new lisp atop the Java Virtual Machine called Clojure. Here's an example of some clojure code that renders a bit of the jobs page, which I'll show you in a moment. See the parentheses: that's how you know it's lisp. Now, this is just a function that takes two arguments; job info, which is a hash map of job attributes, and editable? which is a boolean value describing whether the person viewing the site currently has edit access to the job listing.

Now, how many of you have made websites? How many of you have used a templating language to generate html? Okay, well this is not a templating language. This is just clojure code. This is just a series of nested vectors. And later down the line, it gets passed to a library called hiccup which transforms the vectors into html. But I want to make it clear that this is valid clojure code. I'm not manipulating strings right now. And this is a powerful idea. It means I have all of the faculties for manipulating sequences in the language at my fingertips. This is a toy example, so I'm not making great use of this power here, but you can hopefully imagine the possibilities.

You know what the coolest thing about this code is? It actually renders html both on the server side and on the client side. How is this possible? In 2011, a new implementation of Clojure called ClojureScript was open-sourced. With ClojureScript, you write Clojure code and it gets trans-piled into JavaScript so that it can run in the web browser.

Okay, if that last bit didn't make much sense, don't worry. Now I'm going to briefly show you the StartLabs site to give you an idea of what I'm talking about.

Search frontend...

Questions? Comments? Suggestions?
