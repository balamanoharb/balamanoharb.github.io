---
layout: post
title: What is ECMAScript
date: 2023-10-12 05:30:00 +0530
permalink: what-is-ecmascript
tags: javascript
---

What is ECMAScript? How is it related to JavaScript and its standardization? Let's find out.

## Who owns JavaScript?

JavaScript was named so, purely out of marketing reasons to make use of the gaining popularity of the Java language. So, the only relation JavaScript has with Java is the name alone. This naming has caused decades of misconception about the language.

When LiveScript was renamed to JavaScript, Sun (now Oracle) claimed ownership of the language since the Java trademark was owned by them. With Sun (now Oracle) owning the trademark for JavaScript and Netscape being in the sole possession of the license rights, it only drove other vendors to implement their own version of JavaScript if they wanted to compete in the browser market.

## The need for standardization

When JavaScript was launched officially, with its new features, Navigator browser gained more and more popularity. This, in turn, hardpressed Microsoft into reverse engineering the JavaScript engine and implement their own version of the browser language. Due to trademark issues, Microsoft named their new implementation <a title="JScript" href="https://en.wikipedia.org/wiki/JScript" target="_blank" rel="nofollow noopener">JScript</a>. JScript was first supported in the Internet Explorer 3.0 browser released in August 1996. Since JScript is a different implementation, it ended up creating the browser incompatibilities that frustrated developers for many years to come. It used to be the case, where many websites would include "Best Viewed With Internet Explorer" or "Best Viewed With Navigator" image by default.

![Best Viewed in IE](/assets/images/best-viewed-in-ie.jpg)

With the development of JScript, Netscape strove for standardizing the language. This move would potentially prevent monopoly of the language and prevent vendors from deviating ( defragmenting ) too much from the original language. A standard is essential for a design to mature and grow.  This move also opened up the language to a wider audience, which is very important for the evolution of a language.

## Enter ECMAScript

To standardize the language, Netscape went to several organizations like W3C, ISO and eventually, <a title="ECMA" href="http://www.ecma-international.org/" rel="nofollow noopener" target="_blank"> ECMA International</a> ( an industry association formed in 1961 concerned solely with standardization of information and communications systems ) accepted the proposal put forth for building the standard specification of JavaScript.

For each new specification, the ECMA organization works by having a <em><a title="ECMA standard" href="https://tc39.es/ecma262/" target="_blank" rel="nofollow noopener">standard</a> </em>that serves as an identification for the specification and a <em><a title="ECMA Technical Committie" href="https://www.ecma-international.org/technical-committees/" target="_blank" rel="nofollow noopener">technical committee</a></em> that drives the evolution of the standard.

In case of JavaScript, the standard was called as 
<a title="ECMA-262" href="https://www.ecma-international.org/publications-and-standards/standards/ecma-262/" target="_blank" rel="nofollow noopener">**ECMA-262**</a>
and the technical committee was called
<a title="TC39" href="https://github.com/orgs/tc39/people" rel="nofollow noopener" target="_blank">**TC39**</a>.

The committee released the first edition of the standard (_ECMA-262 Ed.1_) in June 1997. Since the trademark for JavaScript was held by Sun (now Oracle), the specification was called as <a title="ECMAScript" href="https://en.wikipedia.org/wiki/ECMAScript" target="_blank" rel="nofollow">ECMAScript</a>.

![An Excerpt fromm language specification](/assets/images/ecma-262-conformance.png)
_An excerpt from the <a href="https://tc39.es/ecma262/#sec-conformance" target="_blank" rel="nofollow noopener"  target="_blank">ECMAScript latest Language Specification</a>_

After developing the standard based on JavaScript, the specification (language) was named ECMAScript. In turn, JavaScript became its implementation. Basically, JavaScript and JScript are different implementations ( dialect ) of the same specification.

Though Oracle owns the trademark for the name "JavaScript", everyone still uses the name widely when referring to the language. To the contrary, the actual name for the language ECMAScript ( ES ) is used only when referring to the standards and many are not even aware of the name ECMAScript.

## Summary

- ECMAScript - the standard based on which javascript features are implemented.
- Javascript - The programming language that is based on the ECMAScript standard
- Javascript Engines - different implementations of runtime environments that supports javascript execution. Different flavours such as V8, Spidermonkey.

## References

- [ECMAScript spec](https://tc39.es/ecma262/){:target="_blank"}{:rel="noopener noreferrer"}