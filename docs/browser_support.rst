.. This Source Code Form is subject to the terms of the Mozilla Public
.. License, v. 2.0. If a copy of the MPL was not distributed with this
.. file, You can obtain one at http://mozilla.org/MPL/2.0/.


===============
Browser Support
===============

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

Unless there are specific reasons not to, you should look to fully support 
(at the very least) the latest versions of all major browsers (Firefox, Chrome, 
Safari, Opera & Edge), as well as the last 2 versions of Internet Explorer (10 & 11). 
All other browsers can have degraded support.

Don't use proprietary features supported only by a single browser unless
what you're making is a demo of that specific feature. Be mindful when you use
emerging standards supported in some browsers but not others and include fallbacks
for less capable browsers. Check MDN_ or CanIUse_ for compatibility info. If you
use vendor prefixes in CSS, include the prefixes for all supporting browsers as
well as the unprefixed standard.

.. _MDN: https://developer.mozilla.org
.. _CanIUse: http://caniuse.com

Finally, don't rely on user agent sniffing to determine which browsers can and 
can't access a website or use its features. Instead, favor feature detection that 
allows older browsers to degrade gracefully in what they show.