.. This Source Code Form is subject to the terms of the Mozilla Public
.. License, v. 2.0. If a copy of the MPL was not distributed with this
.. file, You can obtain one at http://mozilla.org/MPL/2.0/.


============
Coding Style
============

Code you deliver to Mozilla as a consultant should be written according to
the same standards as code written by any other Mozilla developer. Plan for
your code to be maintained by other coders and comment liberally.

Standardizing a common style for writing and formatting code helps a team
or organization maintain a sensible code base. The goal is consistency and
predictability so that any coder can view the work of another coder and
quickly follow along. We have `documented style guides`_ elsewhere that go
into greater depth, but we'll also summarize the main points here for
some common languages.

.. _`documented style guides`: http://mozweb.readthedocs.org/latest/reference

.. Important::

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

.. Note::

  Using EditorConfig_ in your project can help enforce most of the above 
  rules automatically. You can see an example ``.editorconfig`` file here_.

.. _`EditorConfig`: http://editorconfig.org/
.. _`here`: https://github.com/mozilla/bedrock/blob/master/.editorconfig


`Python <http://mozweb.readthedocs.org/latest/reference/python-style.html>`_
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

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
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

* Use HTML5, with the appropriate doctype: ``<!DOCTYPE html>``
* Omit XML-style trailing slashes: ``<br />``
* Use lowercase for tags and attributes.
* Use double quotes for attribute values.
* `Validate your markup <http://validator.w3.org/>`_.
* Avoid inline or embedded CSS or JavaScript.
* Indent nested elements two spaces; don't use tabs.
* Use the most semantically valuable element suited to the content.


`CSS <http://mozweb.readthedocs.org/latest/reference/css-style.html>`_
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

* Use a linting tool such as `Stylelint <https://stylelint.io/>`_.
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


`JavaScript <http://mozweb.readthedocs.org/latest/reference/js-style.html>`_
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

* Use a linting tool such as `ESLint <https://eslint.org/>`_.
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

