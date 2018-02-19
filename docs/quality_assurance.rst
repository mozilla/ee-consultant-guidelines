.. This Source Code Form is subject to the terms of the Mozilla Public
.. License, v. 2.0. If a copy of the MPL was not distributed with this
.. file, You can obtain one at http://mozilla.org/MPL/2.0/.


=================
Quality Assurance
=================

Who is doing QA and how should be determined prior to a signing a contract or SOW.

Generally there are 2 approaches for QA used with consultants, the first being the most common:

1. Combined QA, Mozilla + Consultant
2. Consultant QA Only

----

-----------------
Combined QA
-----------------

Consultants are expected to deliver working code, however in many cases they do not have the same
standards for QA or expertise to fully deliver a project. In most circumstances we will want to have
MozMeao provide additional QA reviews and testing.

In this scenario you should do the following.

* Request a MozMeao QA Resource:
    * They should review the contract and SOW and determine their level of involvement.
    * They should develop a QA plan that is reviewed and agreed upon by Mozilla and the consultant.

----

------------------
Consultant Only QA
------------------

If the consulting firm is large enough and the project is fully outsourced they may handle the
entirety of the QA process. This must be defined in the SOW along with any project specific areas of
concern. These areas will be specific to the project but some areas to think about are listed below.

* Browser support.
* Mobile support.
* Accessibility support.
* Verifying proper analytics behavior.
* Testing integration with any 3rd party services.
* Load testing.


Even in circumstances where the consulting firm is handling the entirety of the QA, a method for
Mozilla submitting bugs should still be established at Kickoff.
