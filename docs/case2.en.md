\# Case 2: Advanced Web Analytics Setup (GTM + GA4 + Meta Pixel)



!!! abstract "Client Brief (Simulation)"

&nbsp;   \*\*Niche:\*\* B2B SaaS Platform (Lead Generation).

&nbsp;   \*\*Problem:\*\* The client complains about low lead quality and data discrepancies between ad accounts and the CRM. Standard pixel setups only track the final form submission, making it unclear at which stage of the funnel most users drop off.

&nbsp;   \*\*Task:\*\* Build a robust tracking architecture via GTM, set up micro-conversion tracking, and improve data transmission to Meta Ads under iOS 14+ restrictions.



---



\## 🔍 Stage 1: Current State Audit



The analysis of the existing setup revealed the following tracking "holes":

\* GA4 and Meta Pixel codes were hardcoded chaotically directly into the site code without Tag Manager, slowing down page loads.

\* Lack of behavioral tracking: we didn't know if users watched the promo videos or how deeply they read the long-form articles.

\* Data loss due to AdBlockers and browser restrictions (Safari ITP), causing Meta's algorithms to lose about 30% of optimization signals.



---



\## 🛠 Stage 2: Technical Implementation



\### 1. DataLayer Implementation and GTM Migration

\* Migrated absolutely all analytics scripts to \*\*Google Tag Manager\*\*, speeding up site rendering.

\* Created a technical specification (Tech Spec) for developers to implement a custom `dataLayer` object. Now, filling out each step of the multi-screen form sends events to GTM: `form\_step\_1`, `form\_step\_2`, `form\_success`.



\### 2. GA4 Micro-Conversions Setup

Created a series of custom tags and triggers in GTM to track engagement:

\* \*\*Scroll Depth:\*\* tracking scroll at 50%, 75%, and 90% to evaluate blog article read quality.

\* \*\*Video Engagement:\*\* tracking `video\_play`, `video\_progress` (25%, 50%, 100%) events for embedded YouTube players.

\* \*\*Outbound Links:\*\* clicks on messengers and links to partner resources.



\### 3. Meta Conversions API (CAPI) Setup

To solve the data loss issue due to ad blockers, I configured Server-Side tracking:

\* Set up a GTM Server container.

\* Integrated \*\*Facebook Conversions API\*\*, allowing event data to be sent directly from the client's server to Meta's servers, bypassing browser restrictions.

\* Configured the transmission of `fbc` (Click ID) and `fbp` (Browser ID) parameters to increase the Event Match Quality (EMQ) score.



---



!!! success "Implementation Result"

&nbsp;   \* \*\*Data Accuracy:\*\* Data match between ad accounts and CRM increased to \*\*95%\*\*.

&nbsp;   \* \*\*Ad Optimization:\*\* Thanks to Conversions API, Meta algorithms received 30% more data, which helped \*\*reduce CPL (Cost Per Lead) by 22%\*\* in the first month.

&nbsp;   \* \*\*Funnel Analytics:\*\* Created a custom report in GA4 Explorations that clearly shows the "bottlenecks" in the multi-screen registration form.

