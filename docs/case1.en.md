\# Case 1: eCommerce Audit \& Optimization (Shopify + Google Ads)



!!! abstract "Client Brief (Simulation)"

&nbsp;   \*\*Niche:\*\* Outdoor/Camping Gear Store (Shopify).

&nbsp;   \*\*Problem:\*\* Google Ads budget is $2,000/month. Over the past 2 months, overall ROAS dropped from 300% to a critical 110%. Cost Per Acquisition (CPA) doubled.

&nbsp;   \*\*Task:\*\* Conduct an audit of analytics and campaigns (Performance Max, Search), find the cause of the budget drain, and implement solutions to restore ROAS to 250%+.



---



\## 🔍 Stage 1: Deep Audit (What went wrong?)



During the analysis of GA4 and the ad account, I found 3 key issues:



1\. \*\*Budget Cannibalization in Performance Max:\*\* The automated algorithm spent 65% of the budget on cheap, low-margin items (laces, small accessories), ignoring high-margin products (tents, backpacks).

2\. \*\*Junk Traffic in Search:\*\* Search campaigns used Broad Match without a proper negative keyword list. Thousands of budget were wasted on informational queries (e.g., "DIY tent repair").

3\. \*\*Conversion Tracking Failure:\*\* After updating the Shopify code, transactions were duplicated in Google Tag Manager, which broke the learning of Google's smart bidding strategies (the system thought it was generating more revenue than it actually was).



---



\## 🛠 Stage 2: Strategy \& Solution



\### 1. Tech Part: Fixing Analytics

\* Fixed errors in the DataLayer on the Shopify platform.

\* Configured correct conversion value passing via \*\*GTM\*\* to GA4 and Google Ads (eliminated duplicates).

\* Implemented \*\*Enhanced Conversions\*\* for more accurate cookieless user tracking, improving data accuracy by 15%.



\### 2. Performance Max Restructuring (Data-Driven Approach)

Instead of one "catch-all" campaign, I segmented the product feed based on business margins:

\* \*\*Campaign A (High Margin):\*\* Tents, expensive sleeping bags (Set target ROAS: 300%).

\* \*\*Campaign B (Low Margin):\*\* Small gear (Set target ROAS: 150% with a strict budget cap).

\* Optimized product titles in the feed: added brands and key features for better search matching.



\### 3. Cleaning Search Campaigns \& Remarketing

\* Collected over 300+ negative keywords from the search terms report.

\* Moved the highest-converting search queries to Phrase and Exact match.

\* Built a retargeting funnel: created an "Abandoned Cart" audience in GA4 and launched dynamic remarketing in \*\*Meta Ads (Facebook Pixel)\*\* with personalized reminder creatives.



---



!!! success "Optimization Result (First 30 days)"

&nbsp;   \* \*\*ROAS:\*\* Stabilized and grew from 110% to \*\*280%\*\*.

&nbsp;   \* \*\*CPA:\*\* Decreased by \*\*45%\*\* by cutting off irrelevant search traffic.

&nbsp;   \* \*\*Revenue:\*\* The share of sales from high-margin products increased significantly.

