.. This Source Code Form is subject to the terms of the Mozilla Public
.. License, v. 2.0. If a copy of the MPL was not distributed with this
.. file, You can obtain one at http://mozilla.org/MPL/2.0/.


=======
Testing
=======

All code provided by a third party that is intended to be run in a 
production environment should be adequately tested. 

Testing is generally split between two distinct styles:

#. Unit tests can be set to run  automatically against pull requests 
   in GitHub using CI. 
#. Functional tests can be set to run automatically on deployment and 
   run in multiple browsers.


Unit Testing
~~~~~~~~~~~~

* Backend code should be unit tested. For Python we suggest using `pytest`_.
* JavaScript code should also be unit tested. When run in the browser, we 
suggest using `Karma`_ and `Jasmine`_. For Node, either `Mocha`_ or 
`Jest`_ are good options.

.. _`pytest`: https://docs.pytest.org/
.. _`Karma`: http://karma-runner.github.io/
.. _`Jasmine`: https://jasmine.github.io/
.. _`Mocha`: https://mochajs.org/
.. _`Jest`: https://facebook.github.io/jest/


Functional Testing
~~~~~~~~~~~~~~~~~~

* For cross-browser functional testing we suggest using `Selenium`_ 
with `pytest-selenium`_.

.. _`Selenium`: https://docs.seleniumhq.org/
.. _`pytest-selenium`: https://pypi.python.org/pypi/pytest-selenium