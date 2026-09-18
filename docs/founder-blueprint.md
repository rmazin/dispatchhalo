# DispatchHalo

## The automated business

**DispatchHalo is a managed, 24/7 emergency-intake and dispatch service for independent water, fire, and mold restoration companies.** When the client misses a call or closes for the night, an AI agent answers in the client’s name, discloses that it is an automated assistant, identifies the loss type and urgency, checks the service area, opens the job, and pages the on-call technician. A monitored human fallback handles low-confidence calls.

The business is deliberately narrow. It does not sell “AI.” It sells one outcome: **fewer emergency jobs lost to voicemail.**

This is a business blueprint, not a promise of income. The $1 million target is an annualized revenue milestone that still requires founder-led selling, customer proof, reliable execution, and legal review.

## Why this market

- CallRail’s analysis of 1.1 million leads found that home-service businesses miss about **14% of calls** and that **up to 85% of callers whose calls go unanswered will not call back**.
- The U.S. Bureau of Labor Statistics counted about **598,000 specialty-trade contractor establishments** in Q1 2026. DispatchHalo needs only 56 well-chosen customers, not mass-market adoption.
- Housecall Pro’s 2026 research found that **40% of AI-using tradespeople respond faster and lose fewer leads**, while **52% of non-users are unfamiliar with trade-specific AI tools**. That supports a done-for-you service rather than another do-it-yourself app.
- Voice infrastructure is inexpensive relative to the value sold. Retell AI currently lists pay-as-you-go voice agents at roughly **$0.07–$0.31 per minute**; telephony and integrations add cost but leave room for a managed-service gross margin.

Sources: [CallRail benchmark](https://www.callrail.com/blog/callrail-releases-benchmark-report), [BLS specialty trade contractors](https://www.bls.gov/iag/tgs/iag238.htm), [Housecall Pro 2026 AI-in-the-trades report](https://www.housecallpro.com/resources/ai-in-the-trades/), [Retell AI pricing](https://www.retellai.com/pricing), and [Twilio U.S. voice pricing](https://www.twilio.com/en-us/voice/pricing/us).

## Ideal customer profile

Start with one segment only:

- U.S. water/fire/mold restoration company
- 3–30 field employees
- Owner-led or one operations manager
- At least 40 inbound calls per month
- Runs an on-call rotation
- Uses a field-service or CRM system, or can accept jobs through email/SMS initially
- Average emergency job value high enough that one recovered job can cover a month of service
- Poor fit: national franchises with centralized call centers, shops with fewer than 15 monthly calls, or companies unwilling to define service areas and escalation rules

The buyer is the owner or operations manager. Their pain is not “we need AI.” It is “we paid for the lead, the phone rang at 1:12 a.m., nobody answered, and the job went elsewhere.”

## Offer

### Promise

> Every qualified emergency call gets answered, triaged, and handed to the right on-call person—without adding a night shift.

### What the customer receives

1. Conditional call forwarding from the existing business number
2. A branded automated assistant with clear disclosure
3. Trade-specific intake for water, fire, sewage, mold, storm, and non-emergency inquiries
4. Service-area and business-rule checks
5. On-call escalation by SMS and voice, with timed retries
6. Job creation or structured lead delivery into the customer’s existing workflow
7. Call recording/transcript where lawful, with disclosure and retention controls
8. Weekly revenue-recovery report
9. Human fallback for low-confidence or distressed callers
10. Monthly script and routing optimization

### The founding offer

**30-Day Monitored Pilot — $1,500**

- Implementation included for the first ten customers
- Up to 300 answered calls
- One workflow and one on-call rotation
- Daily quality review during week one
- Cancel at the end of the pilot
- No revenue guarantee; DispatchHalo reports answered, qualified, dispatched, booked, and attributed jobs

After ten pilots, move to:

| Plan | Price | Best for | Included |
|---|---:|---|---|
| Response | $1,250/month + usage overage | smaller restoration shop | emergency intake, SMS dispatch, weekly report |
| Dispatch | $1,750/month + usage overage | multi-crew operator | CRM job creation, retry cascade, human fallback, monthly optimization |
| Multi-location | from $3,000/month | regional operator | multiple territories, routing rules, consolidated reporting |

Charge a **$2,500 implementation fee** after the founding cohort. Do not discount the recurring price; reduce scope or offer a shorter pilot.

## $1 million model

The target is **$1 million in annual recurring revenue run rate**, not guaranteed first-year cash collected.

| Metric | Base assumption |
|---|---:|
| Blended monthly revenue per customer | $1,500 |
| Customers needed for $1M ARR | 56 |
| Month-12 target | 57 customers |
| Month-12 MRR | $85,500 |
| Month-12 ARR run rate | $1,026,000 |
| Modeled direct cost per customer | $450/month |
| Modeled gross margin | 70% |
| Target customer acquisition cost | under $3,000 |
| Target monthly logo churn | under 3% |
| Gross-margin CAC payback | under 3 months |

Suggested active-customer sequence by month:

`1, 3, 5, 8, 12, 16, 21, 27, 34, 41, 49, 57`

At $1,500 monthly plus a $2,500 setup fee, that sequence produces roughly **$411,000 of recurring revenue plus $142,500 of setup revenue in year one**, before churn, discounts, refunds, taxes, and bad debt. It reaches a seven-figure annualized run rate near month 12; it does not collect $1 million in year one.

## The automation machine

### Customer delivery

```text
Client misses call / after-hours forwarding
  → automated assistant answers and discloses itself
  → captures name, callback number, address, loss type, timing, insurance status
  → checks service area and emergency rules
  → life-safety issue: fixed “call 911” response; no advice
  → qualified loss: opens job / sends structured lead
  → pages on-call tech
  → no acknowledgment in 3 minutes: second SMS + call
  → no acknowledgment in 7 minutes: backup tech / human fallback
  → customer gets confirmation
  → outcome and attributed revenue flow to weekly report
```

Recommended starting stack:

- Voice agent: Retell AI or an equivalent vendor with webhooks, transfer, analytics, and testing
- Telephony: client-owned number with conditional forwarding; Twilio or the voice vendor for routing
- Workflow engine: n8n
- Lightweight customer and QA database: Airtable or Postgres
- CRM layer: GoHighLevel for the internal sales pipeline; integrate with the customer’s system only after the pilot validates the workflow
- Billing: Stripe subscriptions and metered overages
- Alerts: SMS plus Slack/email for internal exceptions
- Reporting: Looker Studio or a generated weekly email
- Human fallback: trained U.S.-based answering partner, billed into the premium tier

Avoid custom software in the first 90 days. The defensible asset is the restoration-specific workflow library, QA data, integrations, and customer outcomes—not a generic voice interface.

### Internal operations

Automate these events:

- Signed order form → invoice → intake questionnaire → implementation ticket
- Intake completed → agent template cloned → service-area data loaded → test suite created
- Go-live → daily QA queue for seven days
- Low-confidence call, failed transfer, negative sentiment, or policy phrase → human review task
- Weekly → customer scorecard with calls, qualified losses, dispatches, response time, booked jobs, and attributed revenue
- Usage threshold → overage notice and plan recommendation
- 21 days before renewal → automated value summary plus account review link
- Cancellation signal → founder task with call evidence and recovery options

The founder should personally review every call for the first five customers. At 15 customers, review exceptions plus a 10% random sample. At 30 customers, hire a part-time QA operator and keep founder review to escalations and product decisions.

## The call policy

The agent must never improvise safety, insurance, legal, or remediation advice.

Opening:

> Thanks for calling [Company]. I’m the automated after-hours assistant, and this call may be recorded. I can help get your situation to the on-call team. Are you in a safe location right now?

Required intake:

1. Caller name and callback number
2. Property address and ZIP code
3. Active water, fire/smoke, sewage, storm, mold, or other
4. Whether the source is stopped
5. When the damage began
6. Residential or commercial
7. Standing water or affected rooms
8. Insurance claim started: yes/no/unsure
9. Safe access and any immediate hazards
10. Permission to send service updates by text

Fixed safety branch:

> If anyone is in immediate danger, there is active fire or smoke, a suspected gas leak, or someone needs medical help, hang up and call 911 now. I can notify the restoration team after you are safe.

The agent does not promise arrival time, coverage, price, insurance payment, or job acceptance unless the customer has supplied a written rule for that exact condition.

## Acquisition system

### Build a 500-account list

Use public business directories, restoration association directories, local search, and company websites. Collect only business contact data. Score each account:

- +3: advertises 24/7 emergency response
- +2: 3–30 employees
- +2: runs Google Ads or Local Services Ads
- +2: multiple service territories
- +1: reviews mention unanswered phones or slow callbacks
- −3: franchise call center
- −2: no emergency work

Work the highest-scoring 100 first. Do not blast a purchased list.

### Lead magnet

Offer a **Free After-Hours Call Leak Audit**:

- Secret-shop the published number once during permitted evening hours
- Review voicemail, routing, speed, and handoff—not employee performance
- Estimate the number of monthly calls at risk using customer-provided data
- Deliver a one-page findings sheet and a live demonstration using the prospect’s own business rules

Do not make deceptive claims, impersonate a customer with a fabricated emergency, or create operational disruption.

### Cold email sequence

Email 1 — observation:

> Subject: after-hours calls at {{company}}
>
> {{first_name}}, you advertise 24/7 restoration response. When the office line rolls to voicemail, the caller is usually dialing the next company before morning. We set up a monitored after-hours intake layer that answers in your name, qualifies the loss, and pages the on-call tech. Worth showing you a two-minute demo built around {{company}}’s service area?

Email 2 — proof mechanism, three business days later:

> The useful part is not the voice. It is the dispatch chain: service-area check, loss triage, timed technician acknowledgment, backup escalation, and a weekly booked-job report. If you send me your counties and on-call rule, I’ll map the flow before we speak.

Email 3 — close, four business days later:

> I’ll close the loop. If unanswered emergency calls are already covered, no need to reply. If even a few still hit voicemail, I can run a 30-day monitored pilot without replacing your daytime staff.

Include accurate sender identity, a physical mailing address, and a clear opt-out. Suppress opt-outs immediately. Have counsel review outbound practices and the CAN-SPAM/TCPA implications of every channel before launch.

### Cold-call opener

> I’ll be brief. We help restoration owners stop after-hours emergency calls from dying in voicemail. The system answers in your company name, qualifies the loss, and pages your on-call tech; we monitor it for you. I’m not calling to replace your office staff. Who owns after-hours dispatch there?

### Discovery questions

1. What happens to a call at 11 p.m. today?
2. How many inbound calls did you receive last month?
3. What percentage reached a person?
4. Which loss types require immediate dispatch?
5. Who is first and second on call?
6. How fast must someone acknowledge the page?
7. What is one booked emergency loss worth on average?
8. Which system should receive a new job?
9. What must the assistant never say?
10. What evidence would make a 30-day pilot an obvious renewal?

### Close

> Based on your numbers, the pilot has to recover one additional qualified job to be directionally valuable. We will measure answered calls, qualified losses, technician acknowledgments, booked jobs, and attributed revenue. The 30-day monitored pilot is $1,500. If the workflow is safe and useful, it rolls into the monthly plan; otherwise it stops. Shall we map the routing rules now?

## Onboarding checklist

- Legal business name and public-facing name
- Existing number and forwarding provider
- Operating hours and holiday schedule
- Service ZIP codes/counties
- Loss types accepted and excluded
- Residential/commercial rules
- On-call primary, backup, and escalation times
- CRM or job-creation destination
- Approved arrival-time language
- Approved price/insurance language
- Emergency and life-safety phrases
- Recording and disclosure requirements by state
- SMS consent language
- Data-retention period
- Ten simulated calls: five normal, three edge cases, two failures
- Written approval of transcript, scripts, routing, and go-live date

## 90-day founder plan

### Days 1–14: sell before building deeply

- Interview 15 restoration owners or operations managers
- Obtain five anonymized real call-flow examples
- Build one demo line and one dispatch workflow
- Create a 100-account scored list
- Run 20 personalized outreaches per weekday
- Goal: 10 demos and 2 paid pilots

### Days 15–30: create proof

- Launch no more than three pilots
- Review 100% of calls
- Measure answer rate, qualification accuracy, dispatch latency, acknowledgment, booking, and revenue attribution
- Fix the top three failure patterns
- Obtain permission for an anonymized case study
- Goal: 3 paying customers and one quantified result

### Days 31–60: make delivery repeatable

- Convert the best workflow into a template
- Automate onboarding, testing, billing, QA alerts, and weekly reporting
- Add a human fallback partner
- Publish the case study
- Contact 200 additional scored accounts
- Build two referral relationships: restoration marketing agencies and field-service consultants
- Goal: 8–12 active customers

### Days 61–90: build the sales machine

- Hire one contractor for list research and one part-time QA reviewer
- Founder stays on demos and closes
- Standardize the implementation to under four hours of staff time
- Run a weekly webinar: “The 11 p.m. restoration call teardown”
- Offer partners 15% of first-year collected subscription revenue, paid monthly after collection
- Goal: 15 active customers, at least 65% gross margin, and a repeatable path to two net-new customers per week

## Weekly dashboard

Track only metrics that change decisions:

- Accounts contacted
- Positive-reply rate
- Demos booked and attended
- Pilot close rate
- Days from signature to live
- Calls answered
- Qualified emergency losses
- Median technician acknowledgment time
- Booked-job rate
- Attributed customer revenue
- Direct delivery cost per account
- Gross margin
- Logo and revenue churn
- Failure rate by reason

Targets after the first 90 days:

- Positive reply: 5%+
- Demo-to-pilot: 25%+
- Pilot-to-subscription: 70%+
- Go-live: under five business days
- Median on-call acknowledgment: under five minutes
- Critical routing failure: below 1%
- Gross margin: 65%+, moving toward 75%
- Monthly churn: below 3%

## Kill criteria

Do not spend a year forcing a weak idea. Pause or pivot if any of these remain true after 90 days:

- Fewer than 10 of 100 qualified prospects will take a discovery call
- Fewer than 3 of 10 pilots convert to a subscription
- Direct delivery cost exceeds 45% of revenue after workflow tuning
- Restoration owners consistently prefer their existing answering service and will not pay for measured dispatch outcomes
- Safe, accurate routing cannot be maintained below a 1% critical-error rate

The first pivot is adjacent, not broad: emergency plumbers, HVAC contractors, or roofers with the same after-hours dispatch problem.

## Legal and operational guardrails

- This needs business counsel before live traffic. Texts and automated calls can implicate the TCPA; telemarketing generally has stricter consent requirements, and the FCC treats text messages as calls for TCPA purposes. Start with inbound calls initiated by the consumer and transactional follow-up tied to that request.
- Disclose the automated assistant and any recording. Recording-consent laws vary by state; set the strictest practical default and obtain state-specific advice.
- Honor STOP and other reasonable revocation requests immediately across all channels.
- Do not give safety, insurance, legal, health, or remediation advice.
- Use least-privilege access, encrypt data, minimize retention, and keep client workspaces separated.
- Require a human fallback and a manual shutdown switch.
- Review vendor terms, data-processing agreements, incident response, uptime, and number portability before customer launch.

Relevant FCC materials: [TCPA treatment of texts and consent](https://docs.fcc.gov/public/attachments/FCC-23-49A1.pdf) and [revocation of consent rules](https://docs.fcc.gov/public/attachments/FCC-24-24A1.pdf).

## Founder’s next five moves

1. Use **DispatchHalo** only as a working brand until trademark and domain clearance are complete.
2. Create the demonstration line and test the ten-call suite.
3. Interview 15 operators before writing custom software.
4. Sell two paid pilots from a 100-account list.
5. Let measured call outcomes determine whether to scale, change the offer, or pivot.

The strategic thesis is simple: **sell a high-value operational outcome, deliver it with inexpensive automation, stay vertical until the workflow is trusted, and scale only after the first customers prove the economics.**
