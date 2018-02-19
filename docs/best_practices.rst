.. This Source Code Form is subject to the terms of the Mozilla Public
.. License, v. 2.0. If a copy of the MPL was not distributed with this
.. file, You can obtain one at http://mozilla.org/MPL/2.0/.


==============
Best Practices
==============

Websites you design and build for Mozilla as a consultant should adhere 
to the same set of best practices used by Mozilla for its own websites. 
Here are some practices you should follow throughout a project:


Progressive Enhancement
-----------------------

By Default, Mozilla websites should practice `progressive enhancement`_.
Begin with simple, meaningful HTML. Add CSS and JavaScript as progressive
layers in a way that still falls back to usable, accessible content in older
browsers that don't support the latest features or in the event of JavaScript
failing.

.. _`progressive enhancement`: http://alistapart.com/article/understandingprogressiveenhancement

Don't rely exclusively on JavaScript to serve static content. This is less 
about catering to the few people who purposely disable JavaScript and more 
about ensuring some fault tolerance as a best practice. While single-page 
websites that render the entire screen using client-side JavaScript may have 
a place, the reality is that 99% of the time they don't need to be built in 
such a way. If a JavaScript error occurs or someone is using an older web 
browser, their experience should degrade gracefully. No one should be greeted 
by an empty, white screen.


Feature detection
-----------------

Going hand-in-hand with progressive enhancement, Mozilla websites should be 
built using feature detection. Browser sniffing via the user agent string is 
generally considered a bad practise when it comes to determining website 
compatibility. Sites that rely on UA sniffing in order to deliver or block 
content to certain browsers do not meet our quality standards. MDN has a great 
article on how best to `implement feature detection`_ on websites.

.. _`implement feature detection`: https://developer.mozilla.org/docs/Learn/Tools_and_testing/Cross_browser_testing/Feature_detection


Performance
-----------

Mozilla websites should strive to load quickly and be responsive on all types 
of devices, whether it be on desktop, tablet or mobile. Favor server-rendered 
content over client-rendered content. Develop a performance budget for your 
pages during the design phase, and keep a close eye on areas such as page weight, 
and the number of images, fonts, and CSS/JS assets that you use. Use services such 
as `Web Page Test`_ or `Lighthouse`_ to monitor your website performance during 
development. 

.. _`Web Page Test`: https://www.webpagetest.org/
.. _`Lighthouse`: https://developers.google.com/web/tools/lighthouse/

A few general guidelines:

* On a 3G connection, aim for document complete in under 4 seconds, and for the page 
  to be fully loaded in under 6 seconds.
* Keep the number of custom web fonts (including bold and italic variants) to 
  a minimum. 3 web fonts in total (including bold/italic variants), is a good target 
  ceiling. Mozilla websites typically use a combination of `Open Sans`_ and `Zilla Slab`_.
* Avoid large CSS frameworks such as Bootstrap or Foundation as they are by necessity 
  generic and can be heavy-handed.
* Client side JavaScript frameworks should be used as an enhancement, not as the 
  default backbone for delivering content. Large frameworks such as React or Angular 
  should  be used only when they are jointly identified as being the appropriate 
  solution for  a specific requirement.
* Images must be responsive through any combination of CSS, srcset, or SVG. Avoid 
  particularly large images or a large number of images on a page (even if each one 
  is relatively small). Production-ready images should also be optimized and/or 
  compressed as appropriate.

.. _`Open Sans`: http://www.opensans.com/
.. _`Zilla Slab`: https://github.com/mozilla/zilla-slab

A good way to avoid a poorly performing web page is to set a performance budget. 
An optimal goal is to deliver pages at or under a total of 600KB. A reasonable 
breakdown for potential assets would be:

* Fonts - 200KB
* Images - 200KB
* JS - 100KB
* CSS - 20KB

Before you enter the prototyping phase of your project, agree a performance budget 
for your pages and then monitor throughout the development stage.


Accessibility
-------------

Strive to make all Mozilla websites reasonably accessible to people with
disabilities and those using assistive technologies. In many cases this isn't
a matter of adding accessibility features into a site, but simply *not* adding
obstacles that make the site harder to use. Accessible sites are better
for everyone, not only those with disabilities.

A few guidelines:

* Include descriptive ``alt`` text for any meaningful images in HTML.
* Include ``<label>`` elements in forms. Don't use ``placeholder`` as a label.
* Navigation, forms, and interactive widgets like dropdown menus and modal windows
  should be keyboard accessible.
* Ensure sufficient color contrast so text is readable for most users, including
  those with color vision deficiencies.
* Text should be resizable for those who need larger type. Make reasonable allowances
  for text to wrap and reflow when its size changes.
* Include ARIA_ attributes in HTML where appropriate.

.. _ARIA: http://www.w3.org/TR/wai-aria/


Localization
------------

Many Mozilla websites are localized in a large number of locales and different languages. 
If your project has localization (l10n) considerations then there are a few guidelines to 
follow:

* One of the biggest design challenges is ensuring text is both live and expandable. 
  Text included in images or videos is prohibitively time consuming (if not impossible) to 
  localize. The amount of actual text in a given message can vary greatly across languages, 
  meaning the height and width of the surrounding elements must be able to adapt. Precise 
  typography – such as controlled alignment, fitting text in an unusual shape, or specifying 
  where lines should break when text wraps – is often unrealistic. Expect the shape and size 
  of text blocks to change.
* Choose web fonts with broad character sets. Many display fonts only support Roman alphabets 
  and don’t have all the glyphs to correctly render Russian, Swedish, or Polish (for example). 
  Some languages have entirely different alphabets and no one font can serve them all, so 
  expect some languages to be rendered in an entirely different font. Also avoid over-reliance 
  on ALL CAPS or italics, as some scripts don’t lend themselves to these treatments.
* Be considerate about how pages may be read in right-to-left languages, specifically Arabic 
  and Hebrew. Those languages flip the direction of text but also tend to reverse the direction 
  of other UI elements, where objects on the right are seen “first.”
* Avoid symbolism or imagery that might be strongly identified with only one country or nationality 
  (e.g. a bald eagle representing the concept of freedom). People in other countries may not 
  understand such symbols, and at worst they may find them offensive.