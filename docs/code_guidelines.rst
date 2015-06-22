.. This Source Code Form is subject to the terms of the Mozilla Public
.. License, v. 2.0. If a copy of the MPL was not distributed with this
.. file, You can obtain one at http://mozilla.org/MPL/2.0/.


===============
Code Guidelines
===============

Code you deliver to Mozilla as a consultant should be written according to
the same standards as code written by any other Mozilla developer. Plan for
your code to be maintained by other coders and comment liberally.


Code Style
----------

Standardizing a common style for writing and formatting code helps a team
or organization maintain a sensible code base. The goal is consistency and
predictability so that any coder can view the work of another coder and
quickly follow along. We have `documented style guides`_ elsewhere that go
into greater depth, but we'll also summarize the main points here for
some common languages.

.. _`documented style guides`: http://mozweb.readthedocs.org/latest/reference

We urge you to read through the `Mozilla Webdev Bootcamp`_ docs for more
detailed guidelines.

.. _`Mozilla Webdev Bootcamp`: http://mozweb.readthedocs.org/


General
~~~~~~~

* Use spaces for indentation. Never use tabs – history has shown that
  we cannot handle them.
* Use four spaces to indent most languages, but two spaces in HTML. HTML lends
  itself to a lot of nested elements and indenting each level four spaces can
  lead to long lines and messy formatting.
* Wrap lines at 80 characters when possible. HTML is often the exception here
  as well.
* Eliminate trailing whitespace at the end of lines. Blank lines should have
  no spaces.
* Include a single blank line at the end of files.


`Python <http://mozweb.readthedocs.org/latest/reference/python-style.html>`_
~~~~~~~

* Follow PEP8_.
* Follow Pocoo_'s extensions to PEP8, although these are a little less strictly
  enforced across Mozilla projects.
* Check your code against a linting tool. We highly recommend Flake8_ for this.
* Use single quotes unless double (or triple) quotes would be an improvement.
* To continue a new line use a ``()`` not ``\``.
* Indent code with either a hanging indent or a 4 space indent on the next line.

.. _PEP8: http://www.python.org/dev/peps/pep-0008/
.. _flake8: http://flake8.readthedocs.org/latest/
.. _Pocoo: http://www.pocoo.org/internal/styleguide/


`HTML <http://mozweb.readthedocs.org/latest/reference/html-style.html>`_
~~~~~

* Use HTML5, with the appropriate doctype: ``<!DOCTYPE html>``
* Omit XML-style trailing slashes: ``<br />``
* Use lowercase for tags and attributes.
* Use double quotes for attribute values.
* `Validate your markup <http://validator.w3.org/>`_.
* Avoid inline or embedded CSS or JavaScript.
* Indent nested elements two spaces; don't use tabs.
* Use the most semantically valuable element suited to the content.


`CSS <http://mozweb.readthedocs.org/latest/reference/css-style.html>`_
~~~~

* Multi-line rules, not single line.
* Four space indentation; don't use tabs.
* Order declarations alphabetically (with some exceptions).
* Use the simplest, least specific selector possible.
* Make meaningful names, not presentational.
* All lowercase for classes and IDs, no camelCase.
* ID selectors are allowed but use them sparingly and appropriately.
* Don't use ``!important``.
* Use unitless ``line-height``.
* Group related rules into sections.
* Order sections and rules from general to specific.
* `Validate! <http://jigsaw.w3.org/css-validator/>`_

Avoid stock CSS frameworks such as Twitter's Bootstrap_ or Zurb's Foundation_.
These frameworks are great tools for building prototypes, but shouldn't be used
in a production website. A stock framework is by necessity a generic,
one-size-fits-all, off-the-rack solution, not something designed for a specific
purpose and tailored for specific content.

.. _Bootstrap: http://getbootstrap.com/
.. _Foundation: http://foundation.zurb.com/

Most CSS frameworks also come with an over-reliance on presentational classes
to dictate layout and style, permanently coupling structure to presentation.
Want to change the color of a button? You might have to change the class on
every button on the site. That isn't how CSS is supposed to work.

Frameworks tend to include a lot of stuff you won't need for a given project
since they're built to cover every possible situation. Unless you can customize
the build (something the better frameworks offer) you can end up with
unnecessarily bloated cruft. It's often feasible to begin with a stock
framework and customize it to your needs, renaming classes and eliminating
cruft. That may be more efficient than building a system from scratch, depending
on the complexity of the system. Choose wisely.


`JavaScript <http://mozweb.readthedocs.org/latest/reference/js-style.html>`_
~~~~~~~~~~~

* **Always** use `JSHint <http://www.jshint.com/>`_ on your code.
* Assign each variable on a newline, not comma-separated.
* Use ``[]`` to assign a new array, not ``new Array()``.
* Use ``{}`` for new objects, as well.
* Always use semicolons.
* Always use ``===``.
* Always use single quotes.

  * Exception: ``"Don't escape single quotes in strings. Use double quotes."``

* Cache regex into a constant.
* Try to avoid ternaries.
* Check for truthiness, not lack of falseness.


Progressive Enhancement
-----------------------

With few exceptions, Mozilla websites should practice `progressive enhancement`_.
Begin with simple, meaningful HTML. Add CSS and JavaScript as progressive
layers in a way that still falls back to usable, accessible content in older
browsers that don't support the latest features or in the event of JavaScript
failing.

.. _`progressive enhancement`: http://alistapart.com/article/understandingprogressiveenhancement

Don't rely exclusively on JavaScript to serve static content. JavaScript is
a brittle language that can fail to execute in the browser for any number of
reasons. This is less about catering to the few people who purposely disable
JavaScript and more about ensuring some fault tolerance as a best practice.
JavaScript can be a single point of failure. A one-page Ajax website that
requires flawless client-side JavaScript to deliver all of its otherwise static
content (text and images) becomes completely unusable and inaccessible if
there's one error.


Browser Support
---------------

Mozilla websites should be tested in a broad range of browsers, though
that doesn't mean a site must look_ or behave_ exactly the same in all
browsers. Sites should look good and work well in any modern browser, even if
it's not perfectly identical.

.. _look: http://dowebsitesneedtolookexactlythesameineverybrowser.com/
.. _behave: http://dowebsitesneedtobeexperiencedexactlythesameineverybrowser.com/

The current generation of browsers (versions released within the
last few years) are all pretty even in their support of most modern web
standards, but many people still use older browsers and deserve equal
access to information. Consider following a system of `graded browser support`_
wherein the oldest or least capable browsers can still access all the content
and essential functionality, just without all the bells and whistles better
browsers can enjoy. If you use a progressive enhancement methodology, support
for older/other browsers may already be a given.

.. _`graded browser support`: https://github.com/yui/yui3/wiki/Graded-Browser-Support

Don't use proprietary features supported only by a single browser unless
what you're making is a demo of that specific feature. Be mindful when you use
emerging standards supported in some browsers but not others and include fallbacks
for less capabale browsers. Check MDN_ or CanIUse_ for compatibility info. If you
use vendor prefixes in CSS, include the prefixes for all supporting browsers as
well as the unprefixed standard.

.. _MDN: https://developer.mozilla.org
.. _CanIUse: http://caniuse.com

Accessibility
-------------

Strive to make all Mozilla websites reasonably accessible to people with
disabilities and those using assistive technologies. In many cases this isn't
a matter of adding accessibility features into a site, but simply *not* adding
obstacles that make the site harder to use. Accessible sites are better
for everyone, not only those with disabilities.

A few guidelines:

- Include descriptive ``alt`` text for any meaningful images in HTML.
- Include ``<label>`` elements in forms. Don't use ``placeholder`` as a label.
- Navigation, forms, and interactive widgets like dropdown menus and modal windows
  should be keyboard accessible.
- Ensure sufficient color contrast so text is readable for most users, including
  those with color vision dificiencies.
- Text should be resizable for those who need larger type. Make reasonable allowances
  for text to wrap and reflow when its size changes.
- Include ARIA_ attributes in HTML where appropriate.

.. _ARIA: http://www.w3.org/TR/wai-aria/

