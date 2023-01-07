# onboarding
I received a version of this list from a friend who joined as a VP in the Product organization at a previous job and have subsequently expanded on it. My reaction was "who the hell is this guy asking so many questions?", so if that's **your** reaction, I get it! 

There are a few goals with these questions:
1. Build initial knowledge about the business and organization.
2. Learn how Engineering works and interacts with the other parts of the organization.
3. Inform where to ask more questions.

PRs welcome if there are other topics of interest.

# Development

## Code Management
- What kind of version control do we use to manage our code?
- Do we have and follow consistent guidelines for repos, branch strategy, etc.?
- Can everybody discover, access, and contribute to all the code?
- Do we do any changes to code that do not go through a pull request?
- What policies/customs do we have around the PR process?

## Planning and Tracking
- Do we have a defined PDLC/SDLC? What are the steps?
- What language/hierarchy do we use to talk about work? Stories/epics/projects/initiatives/etc. What do each of the terms mean to us?
- Are there formal steps in the lifecycle of a story/work item? What are they?
- Are there standard ways of reporting on the status of work/projects? What variability exists between team/projects?
- What artifacts should be produced during the planning process? What variability exists between team/projects?
- How do we know if a project is on track or not?
- Is there any cadence for the regular review of project status with stakeholders?
- What tools do we use to track work? How well are those tools working for us?

## Developer Ergonomics
- Do we have a standard IDE? What do we use and is this consistent? Who decides? Are other IDEs in use?
- How good is the hardware for the engineers?
- How hard is it to setup a development environment for any particular service? Is the information available to enable anybody to do this successfully and quickly?
- Do we develop behind feature flags, disabled by default? Do we clean these up later or have any way to understand how much debt/cruft exists?
- How easy is it to get work done from the perspective of an engineer on a team?
- Are there any areas where we need to address tech debt?
- Do we have metrics available about the development process itself? Who can access these metrics?
- How long do builds and tests take to run?
- How do we manage the oncall process?

## Architectural and Technology Standards
- How opinionated is our view on the technologies and tech stacks we use?
- How does one go about introducing a new technology or tech stack? Is there any established process or guideline for how this is done?
- Do we have well-defined architectural design patterns we expect all engineers to follow?
- How does the process of technical architecture oversight work? Do we have defined “architects” in teams, do we follow a centralized model, no model at all?

## Security Readiness
- Do we have standards or guidelines for how to architect secure applications?
- Who in the organization is responsible for security? Do we have strategies for app, data, infrastructure, development process security?
- Do we have clear policies around data security, security classification, and how we need to treat each classification while in motion and at rest?
- Do we do automated vulnerability testing during CI? Static analysis? Dynamic analysis? Open source vulnerabilities? Sonarqube?
- Do we do external penetration testing? When was the last test? What were the findings? Is the next test scheduled?
- How prepared are we to prevent, detect, respond to, mitigate, and recover from, a data breach that compromises trust in the system?
- What is the current API security model? How do we handle client auth? How do we handle user auth? How do we handle inter-service call auth and transitive auth chains reliably and securely? What kind of auth do we do internally between services?
- Do we have clear data classification guidelines in terms of risk exposure for personally identified information (PII) and/or regulated data that are clearly and consistently implemented in our services? How do we know we’re compliant?
- Do we have an understanding of what data may be emitted (intentionally or unintentionally) by APIs that could pose a PII or security risk?

## Continuous Integration
- Do we automatically build and run our pipelines upon code commit?
- Do engineers have to setup or manually configure CI’s for new services?
- What do we use to manage our pipelines and execution?
- How much consistency and/or overhead do we have today to maintain CI health?
- Is all our code always able to build successfully? What is the behavior when a commit fails the build/jobs in the CI?

## Testing & Quality
- Is there consistency in how we test today? Unit, component, integration testing? Do we do this universally or is there a lot of variation?
- Where are tests stored? Is this consistent? Do we enable others to run tests for services they do not own?
- How much of our testing is manual vs. automated today?
- Do we do any regular performance testing today? Do we understand scalability limits and actively do load tests to confirm?
- How do we manage test environments? Do individual developers setup and maintain or is there some kind of shared resource we use, especially for integration testing?
- Do we collect test data in any consistent and transparent way? Coverage, success rates, etc.? Where?
- How do we manage device testing for mobile?
- How do we manage browser testing for web?
- How do we manage iOS build infrastructure today? Machines on prem or in cloud?
- Do we consistently test our APIs against their contracts? Is this automated? Do we use any kind of mocking or service virtualization today to enable component testing of APIs?
- Do we test configuration variations prior to deployment?

## Release & Deployment
- Do we have any consistent enforcement of what constitutes “done” for making release decisions in terms of quality, security, testing, etc.?
- Do we have a standard deployment strategy that is designed to minimize the risk of change and preserve the integrity of the production environment?
- Do we have any kind of active/active or other availability zone deployment pattern that allows us to fail away and/or mitigate impact due to change?
- Do we have a consistent and comprehensive change management process and records? Is every change recorded? Does this include infrastructure changes?
- How do we know what code is actually running in production at any given time? Do we have traceability from requirements to code to binaries running in production?
- How automated is deployment? What tools do we use? Do we follow an infra-as-code model? Do we have a true CI/CD automated pipeline or is it still somewhat manual?
- How often do we deploy to the app stores? Is there some known process for this? How do we manage the keys to the Play and App stores?
- Do we leverage a CDN? Do we currently have any business logic in our static assets?
- How do we deploy and/or manage the process of updates? Is this tracked through change management?
- Do we know what our deployment success rate is? How many releases are successful vs. rolled back?
- Is there a separate team or group of people focused on this process or is it totally left up to teams following a DevOps model?

## Business Velocity
- Do we currently measure how many releases or config changes we do that result in a change to customer experience? How often do we push changes to our customers?
- Do we currently measure how long it takes to go from starting a feature to delivering that feature to a customer? (i.e., Lead Time to Change)
- Are there any metrics tracked at the company level about product/engineering effectiveness? What are they? Who has access to the data? How are targets defined? What is the cadence for review of these metrics? How are these metrics produced?
- Are we happy with the current velocity? Are there specific areas where the velocity isn't where we want it to be? What's been the business impact of this mismatch between desire and performance?
- Is there an area where the velocity is perceived as good by the business and sustainable by the team? What leads to these perceptions?

## Operations
- What do we use for logging, log analysis, and alerting? What kind of access policy do we have to production services and access to logs? Is it open to everyone?
- How do we measure uptime/availability and performance of our services? Do we measure availability from an outside-in perspective? How? What is it? Do we have an established SLO and does this propagate to each team that contributes?
- What is the state of basic host hygiene monitoring and alerting? Do we have good coverage of all the basics like disk space, CPU, networking, etc. and associated alerts? Is this universal? Do we respond to these alerts and mitigate in a timely basis? Does this follow a DevOps approach of service owners taking accountability?
- Do we have an operational SLA with any partner? What are the terms? Do we have an ongoing, automated way to measure compliance and/or alert if not?
- Do we have synthetic or end-to-end tests (canary) running continuously in production? If not, do we have any other way to automatically verify major product flows are working as expected?
- Do we have consolidated monitors that tell us the health of all critical systems in one place? Is there anybody actively monitoring holistically across the fleet? e.g., centralized SRE team.
- What is the status of ITSM processes (incident, problem, change)? What tool do we use to track and manage these? Are we able to track corrective actions and measure them all the way to closure?
- Do we have 24/7 monitoring and clear RASCI for production incident management? How do we staff this? How do we feel about our readiness to catch problems before our customers and mitigate them? Do we have 24/7 pager/on-call rotations and coverage? Do we follow a DevOps model that holds service teams accountable for operational continuity?
- Do we know if our fleet is patched and up to date?
- Do we know what the known security exposure is of our fleet at any given time? i.e., sum of known vulnerabilities
- Do we have a process, either automated or manual, to auto patch the production fleet to minimize bugs and security vulnerabilities? What process exists today, if any, to close known security vulnerabilities in production?
- Can we automatically detect abusive behavior and attacks? Are we able to quickly identify and mitigate DDOS and other brute force attacks?

## Data-driven Behavior
- How well do we measure our products today and do we actually set quantitative success metrics and use data regularly to drive product success evaluation and decisions?
- Do we regularly utilize A/B testing or other experiments to validate features and enhancements? What tool(s) do we use to help manage this, if any? Who is responsible for defining experiments?
- How do we instrument our products? What tool do we use for product analytics? Is there consistency and/or guidelines around instrumentation?
- Who generates metrics? Is this the responsibility of each product team to figure it out or is there some standard or accepted way we do this?
- Do we have clearly defined metrics for operational qualities of our products and do we include these as part of the definition of done and the product development process? E.g., error rate, latency, etc.
- How do we measure customer satisfaction of our consumer customers?
- How do we measure customer satisfaction of our partner customers?
- How does customer satisfaction feed back into company/product priorities?

## Bug Management
- How are most production bugs discovered?
- When a production bug is found, what is it’s workflow to find the right owner and get prioritized to fix? Does it end up in the backlog of the right team?
- Do we consistently record bugs we find before releasing and deploying to production?
- Do we have clear classification guidelines for priority/severity of bugs? Do we have SLOs or other expectations around how quickly we fix them?
- Do we have metrics around how many bugs we introduce and how we’re doing managing the introduction of bugs to customers?
- Do we add tests every time we fix a bug to ensure it doesn’t repeat? How universal is this behavior?

# Platform Maturity

## Platform Portfolio
- How well defined are our business capabilities and do we have a clear opinion on the boundaries of each?
- How closely aligned is our technology and services to the business capability model?
- Have we aligned our people and teams to align to the business domain boundaries?

## API Standards
- Do we have clear standards for how we define and develop APIs?
- Do we have a clear versioning and backward compatibility policy for APIs?
- Are we adopting REST, GraphQL, other? For what purpose do we use each and do we have consistency around how we make these decisions?
- Do we have a notion of consistent shared or common components to represent the same entities consistently across different interfaces? E.g., users, accounts, transactions, etc.

## API Infrastructure
- What do we have in terms of API infrastructure? I.e., gateway, app framework support, API discovery site, test frameworks, test tools, mocking, etc.?
- How do we manage the process of exposing new APIs externally?
- How do we handle customer acquisition and onboarding of external API customers? Setup account, get key, access to endpoint, etc.
- Do we have rate limiting, how do we manage auth, etc?
- Do we have an external sandbox or stage environment partners can use to test with? How complete is it in terms of meeting their needs?
- Do we have any way to validate that the service implementation exactly matches the appropriate version of the API contract that we can leverage and enforce as part of quality acceptance?

## Platform Adoption
- When we develop a new feature or capability, do we currently design and plan to use/extend existing platform services and is this process functional and effective? I.e., Does it avoid creation of new tech debt and move fast enough for the business?
- How well does the organization understand the platform mindset? Are we only thinking in terms of solutions or can we think in terms of systems and platforms?
- What does the current customer experience look like for partners or developer customers? Where is the documentation? Do we have samples and guides? Etc.

# People

## Hiring
- Are there any open roles now or planned for the near future?
- Is there a well-defined interview process? What are the steps? What are the artifacts produced during the interview process? How is this process managed?
- Do engineers write code as part of the interview process? Are there standard problems? What tools are used for this?
- Is there an objective rubric by which candidates are scored?
- Do internal participants in the interview process receive formal training?
- Do we track any pipeline metrics associated with the interview process?
- Who is accountable for sourcing candidates?
- How do we decide what level at which a candidate will be hired?
- Do we publish salary ranges on our job postings?
- In which states/countries are we set up to hire?
- What is the process to create/fill/backfill a position?

## Career Management
- Is there a defined career framework? If not, why? If yes, what are the levels and expectations? Do managers and ICs have access to the expectations? Are they regularly used in career conversations?
- What are the formal feedback systems/processes?
- What is the promotion process?
- How frequently do managers do 1x1 meetings with their direct reports?
- Is there policy or philosophy about moving teams?
- Is there a formal methodology used for performance assessments? (9-Box or similar)
- Can engineers move between teams? When was the last time this happened?
- Are we doing any regular assessments of employee engagement/morale/etc?

## Compensation
- Do we have a general philosophy towards compensation?
- Are there formal pay bands? Are the bands publicized internally? How are bands determined?
- How are we accounting for geographic differentials in pay?
- How frequently is pay assessed for an individual?
- How are the bonuses of engineers/engineering managers/product managers calculated? Does everyone understand how their bonus is calculated? Do we regularly hit bonus targets?

## Teams/Organization
- What's the structure of the organization? How do the product and engineering organizations look from a Conway's Law perspective?
- What is the mix of skillsets of the team?
- What is the mix of experience/seniority of the team?
- How long have engineers been on their team?
- What does the leadership bench look like?
- What's the ratio of managers to direct reports? Is this ok?

# Business

## Strategy and Execution
- What's the long term goal of the business? (IPO/acquisition/operate independently indefinitely/preserve optionality and kick ass/etc…)
- What are our mission / vision / values? Are these explicit or implied?
- Are we trying to 10x the business over a period of time?
- What are the current goals/targets/OKRs of the business?
- Who is accountable for each of the goals?
- Do we use a formal methodology for setting/tracking targets?
- How are these tracked? Is the tracking automated? Do we want the tracking to be automated?
- How well does the organization understand the targets? Who has access to how we are progressing to targets?
- What is the process/cadence for setting/reviewing targets?
- What is the behavior when progress towards targets is off track?
- Are targets aspirational where we'd be happy to hit 70% or do we expect to hit 100% of goal?
- What are the targets at the department level?
- What were the targets last year/quarter? Did we hit those targets?
- Is there a difference between the management plan and the board plan for the targets?

## Customer Support
- How do our customers receive support when they run into problems/have questions?
- If the support group needs assistance from the engineering organization, how does this work?
- What system is used to track customer cases?
- What metrics are produced around the support function? Is there a cadence for reviewing these metrics?
- What does the initial customer onboarding process look like?
- How does the support group interact with system data?
- Do we require any investment in new systems?

## Marketing
- Who is accountable for marketing?
- How are changes made to the marketing site?
- Are we happy with the current state of the site?
- What metrics are we tracking for the marketing site? What's used to track these metrics? Are we happy with the current state of the metrics?
- What are the current marketing efforts? How do we judge the effectiveness of our overall marketing efforts?
- Do we require/desire any investments in MarTech?
- What industry events/conferences are important to the business?

## Sales
- What does the current sales pipeline look like?
- How do we define and track the health of the pipeline?
- How does the current pipeline compare to historical trends?
- What systems are used to manage the sales pipeline? Do we require/desire any investments in new systems?
- What involvement does engineering have in the sales process?
- Are new product features/functionality required to complete any deals currently in the pipeline? What's the process to determine feasibility/prioritization of these requests?

## IT
- What's the process to onboard a new employee from an IT/equipment perspective?
- Who manages/maintains the physical infrastructure of the office?
- Who manages employee equipment?
- How do we ensure that our equipment stays up to date from a security perspective?
- What policies exist around employee equipment?
- How do we handle authentication for SaaS systems?
- What does the offboarding process look like for an employee who leaves the organization?
- How do we track which SaaS products are in use?
- Do we require any investment in new systems?

## Legal/Compliance
- Are we involved in any active lawsuits?
- What is the process to negotiate or renew a contract with a vendor?
- What types of regulatory jurisdictions and regulations must we comply with? How prepared are we for audits? Do we have controls documented and can we quickly produce reliable data to back up our stated controls?
- Do we have other contractual obligations we need to meet or comply with (such as with partners) that may not be directly linked to regulations? E.g., process, quality of delivery, downtime, etc.
- Who (or what role) is accountable currently for making sure we remain compliant with regulators?
- Do we require any investment in new systems?

## Finance
- How do we track R&D expenses for tax purposes?
- What policies exist around travel and expenses?
- What is the process to negotiate or renew a contract with a vendor?
- Who can sign agreements?
- What financial reporting is made regularly available to the executive team?
- What are the financial targets for the quarter/year/future?
- Did we hit our financial targets last year/quarter?
- What does the budgeting/planning process look like? Timelines? Key dates?
- What is our fiscal year?
- What are the key financial metrics? What is current state of those metrics?
- Do we require any investment in new systems?
 
## Board
- Who is on the board?
- What was in the last presentation to the board? What information do we consistently provide to the board?
- Who is expected to present to the board?
- When is the next board meeting?
