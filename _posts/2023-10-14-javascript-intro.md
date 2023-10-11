---
layout: post
title:  History of JavaScript - summary
date:  2023-10-14 07:00:00 +0530
permalink: history-of-javascript
tags: javascript
---

JavaScript was created by <a href="https://en.wikipedia.org/wiki/Brendan_Eich" target="_blank" rel="nofollow noopener"> Brendan Eich </a> in 1995 in a span of 10 days. JavaScript has become one of the world’s most popular programming language from being one of the most misunderstood languages. This series of articles will give a sense of why Javascript is the way it is.

> The World's most misunderstood programming language has become the world's most popular programming language.
> -- Douglas Crockford

## The birth of JavaScript

In the early years, the development of JavaScript had a close relationship with the growth of web browsers.

### Browser Beginnings

In early 1991, the first GUI based web browser called the <a title="WorldWideWeb browser" href="https://www.w3.org/People/Berners-Lee/WorldWideWeb.html" target="_blank" rel="nofollow noopener">WorldWideWeb</a> (later renamed to Nexus to avoid confusion) was built by Tim Berners Lee together with Robert Cailliau. It did not support any kind of graphics in its embedded pages. Following Nexus, there were other GUI based web browsers like Erwise and ViolaWWW but they didn’t gain enough popularity.

In the year 1993, the web browser <a title="Mosaic Web Browser" href="https://en.wikipedia.org/wiki/Mosaic_(web_browser)" target="_blank" rel="nofollow noopener">Mosaic </a>was created in <a title="NCSA" href="https://en.wikipedia.org/wiki/National_Center_for_Supercomputing_Applications" target="_blank" rel="nofollow noopener">NCSA</a>. Mosaic is <a title="The first popular Web browser" href="https://www.livinginternet.com/w/wi_mosaic.htm" target="_blank" rel="nofollow noopener">the first popular Web browser</a>, which greatly helped spread use and knowledge of the web across the world. Mosaic is also the first browser to support for showing images.

In the year 1994, with the success of Mosaic, in an attempt to monetize the nascent web, <a title="Jim H.Clark" href="https://en.wikipedia.org/wiki/James_H._Clark" target="_blank" rel="nofollow noopener">Jim H.Clark</a> and <a title="Marc Andreessen" href="https://en.wikipedia.org/wiki/Marc_Andreessen" target="_blank" rel="nofollow noopener">Marc Andreessen</a> the lead developer of the Mosaic browser co-founded <a title="Netscape Communications" href="https://en.wikipedia.org/wiki/Netscape" target="_blank" rel="nofollow noopener">Netscape Communications</a>. Many of the original Mosaic authors went on to work on Navigator, but the two intentionally shared no code. This gave birth to the first browser, <a title="Netscape Navigator" href="https://en.wikipedia.org/wiki/Netscape_Navigator" target="_blank" rel="nofollow noopener">Netscape Navigator</a>. The initial version didn’t have support for any built-in language yet.

Netscape soon realized that the Web needed to be more dynamic in order for the web pages to be more interactive. Netscape wanted it to work like <a title="HyperCard" href="https://en.wikipedia.org/wiki/HyperCard" target="_blank" rel="nofollow noopener">HyperCard</a>, a programming tool developed by Apple. For this purpose, it needed a programming language to be put in the web browser to interact with the static HTML.

In <a href="https://www.computerworld.com.au/article/255293/a-z_programming_languages_javascript/" target="_blank" rel="nofollow noopener">April 1995</a>, Netscape recruited <a href="https://en.wikipedia.org/wiki/Brendan_Eich" target="_blank" rel="nofollow noopener">Brendan Eich</a> with the <a title="Popularity" href="https://brendaneich.com/2008/04/popularity/" target="_blank" rel="nofollow noopener">promise</a> of letting him implement scheme (a Lisp dialect) for the browser in order to realize the vision of making the web more dynamic.

It was around the same time that Microsoft had entered the browser market with its own browser, Internet Explorer 1.0 in August 1995. With Microsoft joining the browser market and others marching in, the pressure for constant improvement of browser features increased tremendously. This heavy competition for the browser market would later be known as the <a title="browser wars" href="https://en.wikipedia.org/wiki/Browser_wars" target="_blank" rel="nofollow noopener">browser wars</a> ( a <a title="browser wars documentary" href="https://www.youtube.com/watch?v=VANORrzKX50" target="_blank" rel="nofollow noopener">documentary</a> on the same).

### Enter JavaScript

Before Eich could implement Scheme for the browser, Netscape had joined hands with the Sun Microsystem (now Oracle) to stand off against Microsoft and other competitors. With this union, the question "why two languages? why not just Java?" was hotly debated within Netscape. And the answer as follows:

> The answer was that two languages were required to serve the two mostly-disjoint audiences in the programming ziggurat who most deserved dedicated programming languages: the component authors, who wrote in C++ or (we hoped) Java; and the “scripters”, amateur or pro, who would write code directly embedded in HTML.
> -- Brendan Eich [ from Eich's blog post <a href="https://brendaneich.com/2008/04/popularity/" target="_blank" rel="nofollow noopener">popular</a>

The Netscape management had also agreed that the new language would be a little brother of Java, like how Visual Basic was to C++. With this new constraint the syntax of the language to be used in the browser couldn’t be too different from Java and so it ruled out the possibility of other languages such as Perl, Python, and Tcl, along with Scheme as well to be a language candidate. Because of these reasons, what was to be a scheme of browser ended up being a companion scripting language for Java.

Under these circumstances, there was a lot of pressure to get the working prototype out and prove the concept for the new language. Eich started developing this new language based on his inspirations from Java, Scheme, and Self.

> If I had done classes in JavaScript back in May 1995, I would have been told that it was too much like Java or that JavaScript was competing with Java … I was under marketing orders to make it look like Java but not make it too big for its britches … [it] needed to be a silly little brother language.
> -- from <a href="https://www.computer.org/csdl/mags/co/2012/02/mco2012020007.html">computer.org</a>

Eich came up with the working prototype for the scripting language in 10 days. Marc Andreessen codenamed the language as "Mocha". With rapid prototyping, Mocha had proved itself by successfully integrating into Navigator 2.0, which was in its pre-alpha development phase.

> **Were there any particularly hard/annoying problems you had to overcome in the development of the language?**
> Yes, mainly the incredibly short development cycle to prove the concept, after which the language design was frozen by necessity.
> --Brendan Eich [ from <a title="The A-Z of Programming Languages: JavaScript" href="https://www.computerworld.com.au/article/255293/a-z_programming_languages_javascript/?pp=2" target="_blank" rel="nofollow noopener">The A-Z of Programming Languages: JavaScript</a>]

Netscape marketing changed the name to LiveScript because it already had several products with the prefix “Live”. In early December 1995, Netscape and Sun Microsystem closed the deal. To ride along the Java popularity, the marketing team renamed the language again to its final name, JavaScript.

**Thus JavaScript was born.**

### Sources

- <a title="Crockford on JavaScript - Chapter 2" href="https://www.youtube.com/watch?v=RO1Wnu-xKoY" target="_blank" rel="nofollow noopener">Crockford on JavaScript - Chapter 2</a>
- Infoworld - <a title="JavaScript creator ponders past, future" href="https://www.infoworld.com/article/2653798/application-development/javascript-creator-ponders-past--future.html" target="_blank" rel="nofollow noopener">JavaScript creator ponders past, future</a>
- Computerworld - <a title="The A-Z of Programming Languages: JavaScript" href="https://www.computerworld.com.au/article/255293/a-z_programming_languages_javascript/" target="_blank" rel="nofollow noopener">The A-Z of Programming Languages: JavaScript</a>
- Brendan Eich’s blog - <a href="https://brendaneich.com/2008/04/popularity/" target="_blank" rel="nofollow noopener">Popularity</a>
- Computing conversation with Brendan Eich [<a href="https://youtu.be/IPxQ9kEaF8c">youtube</a>]
- <a title="A brief history of javascript" href="https://auth0.com/blog/a-brief-history-of-javascript/" target="_blank" rel="nofollow noopener">A brief history of javascript</a>
