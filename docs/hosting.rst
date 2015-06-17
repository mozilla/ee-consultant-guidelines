.. This Source Code Form is subject to the terms of the Mozilla Public
.. License, v. 2.0. If a copy of the MPL was not distributed with this
.. file, You can obtain one at http://mozilla.org/MPL/2.0/.


===============
Hosting
===============

There are 2 common scenarios for hosting a project developed by consultants.

1. Consultant Hosted
2. Mozilla Hosted

----

-----------------
Consultant Hosted
-----------------

Consultant hosted means the 3rd party is taking responsibility for hosting the website. The
project is not hosted on Mozilla hardware and Mozilla is not responsible for either
performance or uptime.

The following responsibilites should be outlined in a SOW:



**Consultant Responsible**

* Billing, either direct or pass through.
    * Include duration of hosting.
    * Provide estimates of all costs (hosting/bandwidth/other) including any possible overages.
* Ensuring hosting is performant.
    * Ensure project can handle expected traffic.
    * Ensure uptime for duration of project.


**Mozilla Responsible**

* Domain Configuration:
    * Registration of any domains.
    * DNS & SSL for any domains.

----

---------------
Mozilla Hosted
---------------

Mozilla hosted means the project is hosted on Mozilla hardware. Mozilla is responsible for providing
performant hosting.

The following responsibilites should be outlined in a SOW:

**Consultant Responsible**

* Delivering Code:
    * Deploying and configuring code that works properly on Mozilla's Infra.
    * Ensuring project works as intended on Mozilla Infra.


**Mozilla Responsible**

* Providing Infrastructure & Documenting Environments & Deployment:
    * Registration of any domains.
    * DNS & SSL for any domains.
    * Providing (if needed) dev, stage and production hosting.
    * Documentation on how code will be deployed to each environment and by whom.
    * Any specific implementation details specific to Mozilla infra.
