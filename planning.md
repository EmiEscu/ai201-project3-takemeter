# TakeMeter — planning.md

---

## Community: 

**The reason I chose: r/csMajors**

The community that I chose for this project was `r/csMajors`. The reason why I chose this subreddit is because most of the information that it contained was textual. On top of the information being textual I am a CS Major myself so I am already familiar with the terminology this subreddit has and I thought I could inform myself and what such a subreddit contained.


**Why is this community a good fit for a classification task**


1. Built-in "Ground Truth" Labels
    Some posts in the community already include flairs and there are centralized megathreads (like the weekly "Resume Review/Roast," "Project Showcase," or company-specific threads). For training a model or building a machine learning pipeline, these structural elements act as clean, pre-labeled training data. This saves me some time as now I don't have to manually tag 200 posts to teach the model what a "Resume" or "Interview" post looks like; the subreddit's moderation has already done the labeling.  
    
2. Distinct Intent Categories
    Because the stakes are high (careers and degrees), users post with very clear, identifiable goals. The discourse naturally segments into functional buckets: asking for actionable advice on a project, resource sharing, seeking emotional support, or debating the value of a specific degree path. This makes setting up multi-class intent detection straightforward.

---

## Labels:

Do not classify based on keyword matching (e.g., seeing the word 'interview' and picking Label 3). Classify based strictly on the intent and the current pipeline state of the author.

There is exactly one organizing question, applied as a cascade. Walk it top to bottom and **stop at the first YES**. This guarantees every post gets exactly one label.

**Always read the full label definition before settling on a boundary ruling. The cascade tells you which label to land on, but the label definition tells you whether the post actually fits. If the definition explicitly covers the post type, the definition wins over a surface read of the boundary rule.**

```
STEP 1 — Is the author broadcasting/expressing, rather than trying to solve a personal problem?
         (venting, flexing, celebrating, debating, polling, telling a story, seeking validation/commiseration)
         YES → LABEL 1: Venting & Commentary
         NO  → continue

STEP 2 — Is the post anchored to a SPECIFIC live hiring-pipeline event?
         (an interview, an OA/application, a recruiting timeline, or an offer-in-hand to weigh/negotiate)
         YES → LABEL 3: Applications, Interviews & Offers
         NO  → continue

STEP 3 — Is the post about handling a situation INSIDE a role the author currently holds or has accepted?
         (return offers, manager/team/project struggles, tenure, extending, career strategy from within)
         YES → LABEL 4: Internship & Workplace Situations
         NO  → continue

DEFAULT — LABEL 2: Skills & Study
         (how to learn/build/study/position yourself, what path to take, academics, breaking in, recovering)
```

Why this order: the #1 source of mislabeling is a **vent disguised as a question** ("…anyone else?"), so Venting is filtered first. Skills & Study is last not because it's a junk bucket — it has a real positive definition — but because it's the broadest *developmental* category and correctly absorbs anything that isn't expressive, pipeline-specific, or in-role.

---

## The 4 Labels

### LABEL 1 — Venting & Commentary
**Boundary (one sentence):** The post's purpose is to express, broadcast, debate, or be heard — if the community posted zero replies, the post would still have served its purpose.

**Covers:** rants about the market or culture; despair/burnout; success-story "here's how I did it" flexes; celebrations ("I landed an interview!"); hot takes and opinion pieces; market-trend arguments; "anyone else feel…?" commiseration; salary/experience polls; meta posts about the sub; storytelling.


**Signals:** strong emotion carries the post; an "About Me" credential block set up before delivering advice; quoted dialogue ("then he said…"); an aphoristic mic-drop closer instead of a real question; rhetorical or permission-seeking questions ("is there anything stopping me?"); structured data requests ("share your: title / TC / location"). Rhetorical, permission-seeking, or unanswerable questions (e.g., 'Am I cooked?', 'Is it over for me?', 'Anyone else in the same boat?', 'Is there anything stopping me from quitting?'). Ignore question mark and evaluate if actionable technical/career advice can actually be given. If the answer is just commiseration, it is Label 1.

**NOT this if:** the author genuinely needs information back to make a decision or solve a problem. A charged post that drives toward a real, answerable question belongs in 2, 3, or 4.

**Ex1:**
```

"I just was meeting up with someone I know who is working as a big tech SWE intern. I was telling them about my sister who’s working towards becoming a
trauma surgeon (a type of doctor that treats stuff like vehicle accident or assault injuries, etc). His first reaction was: “why doesnt she js go into
tech for the TC? med school lwk expensive. its ezier js to internshipmax and retire early from big tech promos”. . . You’re a HUMAN. You will DIE. On 
your deathbed, are you really going to fucking be thinking about the shitty levels.fyi salary page?! Or are you going to be desperately pleading to that
trauma surgeon to do anything they can so that you can live to see the sunset another day. Just think about that. FUCKKKKK" 
[https://www.reddit.com/r/csMajors/comments/1udruwf/genuine_crash_out/]

```

**Ex2:**

```
"Went to a hackathon with a friend and we met a guy from BlackRock.
The moment my friend found out where he worked, he started treating him like some final boss of tech. Started asking for everything, LinkedIn, Twitter 
GitHub, resume, how many LeetCode problems he’d solved, Codeforces rating, what stack he uses, all of it.
The BlackRock guy answered everything calmly and then left.
As soon as he walked away, I said, “Doesn’t BlackRock pay kinda low though?”
My friend looked at me like I had just destroyed his whole career plan.
Never seen someone switch from worship mode to existential crisis that fast." 
[https://www.reddit.com/r/csMajors/comments/1uefju8/the_moment_my_friend_found_out_he_worked_at/]

```

---

### LABEL 2 — Skills & Study
**Boundary (one sentence):** The author is optimizing *themselves* — what to learn, build, study, or how to position their candidacy — with no specific live interview/offer and not from inside a current role.

**Covers:** learning roadmaps and resource requests; project ideas / "is this project worth building"; resume and positioning help; "how do I become competitive"; job-search strategy in general (where to apply, why am I getting screened); academic questions (courses, professors, math, major choice, research direction); pre-enrollment prep; learning-method and "am I behind" study questions; re-entry/upskilling after a gap; career-path direction choices for someone breaking in; the timeline is used as a planning input for a study or academic roadmap.

**Signals:** asks for guides, courses, roadmaps, what-to-build; describes current skill level and a gap to close; companies named as **aspirational targets**, not current employers; the answer would be a list of things to learn/do/study.

**NOT this if:** the post hinges on a specific scheduled interview/application/offer (→ 3) or on handling a role the author already holds (→ 4).

**Ex1:**

```
"Along with attending my class of Systems Programming I took initiative and created a project of making a custom *shell (more information below). I know
I could just keep it to my portfolio for reference but my main goal is to approach the said Professor for a future undergraduate thesis or maybe take part
in their research group .
Should I make an effort and show them my work or is it better to wait until I actually decide to start on my thesis ? In what context should I do that ?
Is it common practice for students to send their projects to their Professors? Any info would be helpful .
About the project :
I built a custom shell that becomes an "interactive textbook" . Its main purpose is to teach a concept and then have the student apply it , as an
exercise , in the terminal . It checks their work , gives feedback etc. It basically supports all basic Unix commands and has , also , it's own
"commands" . It provides all theory and code given in class , as well as , additional advanced concepts and exercises." 
[https://www.reddit.com/r/csMajors/comments/1ued302/how_should_i_approach_a_professor_for_academic/]

```


**Ex2:**

```
"I’m a CS student and I’m trying to figure out the best path to become genuinely competitive for AI/ML internships and eventually AI engineering roles.
What confuses me is that everyone says “just build projects,” but I feel like I’m missing the bigger picture. I can follow tutorials and build random
projects, but I don’t feel like I actually understand the AI landscape well enough to know what skills employers are looking for or what projects are
worth building.
My goal is to become highly skilled in modern AI, including:
LLMs and Transformers
RAG systems
Agentic AI
Multi-agent systems
Tool use / function calling
MCPs and AI workflows
Fine-tuning and evaluation
AI engineering and deployment
Traditional ML and deep learning fundamentals
Are there any courses or like learning paths that would give me a structured understanding of the field from fundamentals all the way to building
production-level AI systems?
If you were a CS student in 2026 aiming for AI internships at places like NVIDIA,Andurilwhat would your roadmap look like?"
[https://www.reddit.com/r/csMajors/comments/1uek83o/how_would_you_learn_ai_from_scratch_if_your_goal/]

```


---

### LABEL 3 — Applications, Interviews & Offers
**Boundary (one sentence):** The post MUST be anchored to a currently acitve **specific, concrete point in the hiring pipeline** — a real interview, application/OA, recruiting timeline, or an offer in hand. 

**Covers:** "what's the X interview like / what questions to expect"; interview experiences and "is this normal?"; OA/assessment questions and anxieties; application/recruiting status and timing ("when do fall interviews start," "indefinite delay after verbal offer," team-matching limbo); offer comparisons and decisions ("which offer should I take"); comp negotiation on an offer; visa/OPT/start-date logistics tied to a specific offer not yet started.

**Signals:** a named company + a named stage (OA, phone screen, onsite, loop, team match, offer); a date or deadline; "has anyone interviewed with…"; weighing Offer A vs Offer B.

**NOT this if:** there's no specific live process event (live event is anything current or about to be current) and it's about general competitiveness (→ 2), or the author has already started the role and is navigating life inside it (→ 4). The post is about general job market struggles, asking how to get interviews, asking for referrals, or broad interview prep without a specific company/date. The mere presence of the words 'interview', 'resume', or 'application' DOES NOT make it Label 3. If there is no active application, scheduled interview, or pending offer on the table, push to Label 2.

**Ex1:**

```
"I currently have two offers:      IBM in the middle of no where (Junior Cloud position)      Small company (around 400 employees) in Pittsburgh area. (Software Test Engineer)  I know there is a debate in the career paths themselves, but I’m currently debating if the resume value of IBM brings more opportunity or being located in a decent tech hub does. These positions are very similar in pay.  I would prefer to move into SWE, but prefer the Cloud position over the Test Engineer position. I believe the test position would give me a path to SWE whereas the Cloud position would likely not. Overall, for this debate I am unsure which position brings me better career trajectory overall."
[https://www.reddit.com/r/csMajors/comments/1uel4gn/big_name_bad_location_vs_small_name_good_location/]

```

**Ex2:**

```
"Hi, I am a CS major who graduated this past December. After about 5 months of applying and interviewing, I was able to secure two offers. I am extremely grateful, as I was honestly getting so tired of the job hunt; this was a massive break for me. However, I now have a dilemma regarding which offer to accept.  I have a lot of people in my ear telling me that IBM will look incredible on my resume, and that I should drop everything to go there. Any advice would be great. Everyone in my life is pushing me to choose IBM and practically calling me dumb if I don't pick IBM, but I honestly don't know if a company's name carries that much weight on a resume anymore.  Fortune 500 Company  Position: SWE (Atlanta)  76.5k + 5% Bonus of salary given at end of year every year  Pros:  - Will not have to relocate can live at home with parents (save) and if I wanted to move out rent is affordable.  - Know my manager and the team. Vibes are great.  - Big emphasis on Work Life Balance by the manager  - Hybrid 2 days in office, but is flexibility and could be less.  - Start date is soon  Cons:  - Not a big tech name like IBM  IBM  Position: Data Engineer Future Now CIC (Chicago)  85k + 3k sign on bonus  Pros:  - Big tech name  - Better Salary  - Living and exploring a whole new city  Cons:  - Not SWE, but data engineer title  - Almost 2k in rent in Chicago for a studio  - I do not know my team or manager.  - Start date is not for awhile  UPDATE: Thank you everybody for the advice I really needed it and appreciate it! I am going with offer 1 with the Fortune500 as I like the WLB, the team, manager and the work I would be doing. The work is full range of a lot of things backend infrastructure , digital marketing, data pipelines, ai agents and a lil bit of consulting. So I feel I would be able to learn a lot and pivot if I ever want to in the future. As before thank you again to everybody!"
[https://www.reddit.com/r/csMajors/comments/1u9h5cn/offer_dilemma/]
```

---

### LABEL 4 — Internship & Workplace Situations
**Boundary (one sentence):** The author is **already in (or has accepted) a role** and needs to navigate something happening inside it. The state of being employed overrides the subject of the post if its not used as BACKGROUND information. Even if the user is asking a technical coding question or asking about applying to other jobs, if the problem originates from inside an ACTIVE, ACCEPTED role, it is Label 4.

**Covers:** securing a return offer while interning; manager/team/mentor dynamics; "I can't finish my intern project"; whether quitting/extending/deferring is okay *once you're in*; first-week/onboarding struggles; tenure norms and job-hopping after accepting; "I broke in, now what" career strategy from within an accepted role; processing/learning from a role that just ended.

**Signals:** present/recent-tense descriptions of being in the role ("my manager," "I'm currently interning," "I start in a week," "my internship ended"); the problem only exists because the author holds the position. Keywords like 'my manager', 'my team', 'my codebase', 'my intern project', or 'my onboarding'. If these appear, the user is already through the door.

**NOT this if:** the author hasn't started and is *deciding whether to accept* (that's an offer decision → 3), or the role is just backstory for a general competitiveness/learning question (→ 2).

**Ex1:**

```
" Anyone else feel like they aren't going to finish their intern project? I'm the first intern my team has had, so I guess the team isn't really 
accustomed to interns. My manager even said I might not even finish it or I might, who knows.

It's turning out to be more complicated then I initially thought as well, as I'm working through the design, plus working in the codebase is hard since I 
don't understand any of it, since its full of abstractions.

My manager seems like he does want to bring me on full time (he's mentioned this twice alr), but like if I can't even finish the intern project, why even 
bring me on.

I'm starting my third week this week, I guess it's my second 'real' week since the first week I was stuck doing intern orientation stuff. I also still 
trying to get all the access stuff for aws and more, so that's also an issue. I only have 7 more weeks, time is flying.

Has anybody experienced this before? I feel like all I hear is that everyone finishes their intern project."
[https://www.reddit.com/r/csMajors/comments/1ubtqf8/intern_project/]

```

**Ex2:**

```
Was extremely lucky to get a faang+ swe internship and a return offer. What’s the best path to ensure job security? Stay at the company for as long as 
possible, or build up my resume? What’s the safest route?
[https://www.reddit.com/r/csMajors/comments/1uac9kg/broke_into_faang_now_what/]

```

---

## Decision rules for the three real boundaries

These three pairs are where annotators will actually disagree. Each has a one-line tiebreaker.

**1 vs (2/3/4) — vent or genuine ask?**
Remove the replies. If the post still did its job (the author got to express/flex/be heard), it's **1**. If the post is incomplete without answers, it's an advice label. Tell: rhetorical/permission questions and mic-drop closers → 1; specific answerable questions → not 1.

**3 vs 4 — applying or employed?**
*Have they started / accepted the role ?* Not yet, still choosing or interviewing → **3**. Already in it (or accepted and now navigating it) → **4**. So "defer my Amazon offer" = 3 (not started); "extend my internship" = 4 (currently interning).

**2 vs 3 — general competitiveness or a live event?**
Is there a specific scheduled interview / application / offer on the table? Yes → **3**. No — it's about your profile's general competitiveness or what to do/learn — → **2**. So "how much does FAANG on my resume help future recruiting?" = 2 (no live event); "Cloudflare interview June 29, what's round one?" = 3.

---

## Hard edge cases 

| Post | Title (short) | Looks like | Label | Why |
|---|---|---|---|---|
| [https://www.reddit.com/r/csMajors/comments/1udwoe4/can_i_just_quit_my_internship/] | Can I just quit my internship | 4 | **1** | Plan already detailed; "anything stop me?" is permission-seeking, not a real ask |
| [https://www.reddit.com/r/csMajors/comments/1uac9kg/broke_into_faang_now_what/] | Broke into faang, now what? | 3 | **4** | Return offer accepted → strategy from *inside* an accepted role |
| [https://www.reddit.com/r/csMajors/comments/1ubbqxm/how_much_does_faang_move_the_bar/] | How much does FAANG move the bar? | 3 | **2** | No live process event; it's about general competitiveness/profile value |
| [https://www.reddit.com/r/csMajors/comments/1ubw97s/amazon_fall_internship_delays_grad_1_semester_vs/] | Amazon internship vs stay on current track | 4 | **3** | Currently interning, but the live decision is whether to *accept another offer* |
| [https://www.reddit.com/r/csMajors/comments/1u9pe4b/new_grad_job_search_is_seriously_affecting_my/] | New grad mental health / how are you dealing | 1 | **2** | Leads emotional but pivots to "what actually worked" — asks for tactics |
| [https://www.reddit.com/r/csMajors/comments/1ueufjs/who_to_believe/] | Who to believe (AI coding) | 2 | **1** | Identity/opinion discussion, not a concrete learning request |
| [https://www.reddit.com/r/csMajors/comments/1uambba/cs_new_grad_looking_for_advice_about_job/] | CS New Grad looking for advice about job | 3 | **4** | Already accepted, starts in a week → tenure/in-role question |


## Made up Edge Cases

| Text | Looks like | Label | Why |
|---|---|---|---|
|"I'm 6 weeks into my Salesforce summer internship and I just received an offer from Amazon for a fall co-op. Hard deadline is this Friday. My Salesforce manager has been dropping hints about a return offer but nothing official. Do I ask my manager directly before the Amazon deadline? Or do I take the Amazon offer as a safety net? Scared of burning the bridge either way."| 3 | **4** | There's a live offer with a hard deadline, which screams Label 3. But the tie-breaker applies: "Have they started / accepted the role yet? Already in it → 4." The Salesforce internship is the active role. The Amazon offer is a complication arising *inside* that situation, not a standalone pipeline decision. |
|"I signed an offer with Capital One last week because the deadline was exploding, but I literally just got the Google team match email this morning. If I match with a team at Google, is it career suicide to renege on Capital One? I know I technically already committed to C1 and I start onboarding next month, but Google is my dream company. How do I navigate this without burning bridges?"| 4 | **3** | Looks like Label 4 because C1 is signed. But "I start onboarding next month" = not yet in the role. The post is anchored to a live Google team match with a real, time-sensitive pipeline decision. Signed ≠ started — the role hasn't begun, so this is still a hiring-pipeline event → Label 3. |
---

## How to label any new post in 10 seconds
1. Strip the emotion. Ask: *does the author need an answer to act, or are they expressing?* → if expressing, **Label 1**, done.
2. Is there a specific interview/application/offer in play? → **Label 3**.
3. Are they already in the role, asking about life inside it? → **Label 4**.
4. Otherwise it's about getting better, getting in, or school → **Label 2**.

---

## Data collection plan: 

Where will you collect examples? How many per label? What will you do if a label is underrepresented after 200 examples?

Sources: 
    ~200 posts/comments from `r/csMajors`, pulled from `Hot`, `Rising`, `New`, and `Top`  

Data extraction approach

    Manually downloaded JSON formatted versions of the posts.
    Total target: ~200 examples 

CSV format

Columns: id, title, text, label
Label distribution targets
Label 	Target % 	Target count (of 200)
Venting & Commentary 	~20% 	40
Skills & Study 	~35% 	70
Applications, Interviews & Offers 	~35% 	70
Internship & Workplace Situations 	~10% 	20

Why it's better to have a high concentration of label 2 and label 3:

I want the model to know how to properly differentiate between general competitiveness vs live events. It's more than likely that `Internship & Workplace Situations` will be underrepresented, but that is okay since it should be a lot easier to distinguish between the rest of the labels.

Imbalance mitigation

    If `Internship & Workplace Situations` falls below 20 examples, manually collect additional megathread comments or search for standalone project posts
    If any single label exceeds 70%, redistribute by collecting more from underrepresented sorts/sources

Labeling workflow

    Manually download raw examples in JSON format and use Gemini to assemble them into a CSV.
    Pre-label all examples using LLMs (Gemini 3.1 Pro) with the exact label definitions from this document.
    Manually review every single pre-labeled example, correcting labels as needed.
    Document at least 3 genuinely difficult labeling decisions.


---

## Evaluation Metrics

Primary metrics

    Overall accuracy for both fine-tuned model and zero-shot baseline
    Per-class F1 score — the most informative single metric per label because it balances precision and recall. This is critical because label distribution is intentionally uneven (Venting & Commentary at ~20% and Internship & Workplace Situations at ~10% vs. Skills & Study and Applications, Interviews & Offers at ~35% each), so raw accuracy alone would mask poor performance on minority classes.

Secondary metrics

    Precision and recall per class — to diagnose whether the model is being conservative (high precision, low recall) or over-predicting (high recall, low precision) for each label
    Confusion matrix — to identify which specific label pairs the model confuses most. We expect Skills & Study ↔ Venting & Commentary (vent disguised as a question) and Skills & Study ↔ Applications, Interviews & Offers (general prep vs. live event) to be the most confused pairs.

**Why these metrics**

Overall accuracy provides a single headline number useful for comparing the fine-tuned model against the zero-shot baseline, but it is misleading on an imbalanced dataset. A model that always predicts the two majority classes (Skills & Study and Applications, Interviews & Offers at ~35% each) would achieve roughly 70% accuracy while being completely blind to Venting & Commentary (~20%) and Internship & Workplace Situations (~10%). Per-class F1 is the primary interpretability metric because it measures performance on each label independently, penalizing both false positives and false negatives — making it impossible to hide poor performance on minority classes behind strong performance on majority ones.

Precision and recall per class serve as the diagnostic layer beneath F1. If a label's F1 is low, precision vs. recall breaks down *how* it is failing: a model over-predicting Venting & Commentary (Label 1) shows high recall but low precision for that class; a model being too conservative about flagging it shows the opposite. The confusion matrix maps the actual failure topology across all four label pairs — we specifically expect the Skills & Study ↔ Venting & Commentary and Skills & Study ↔ Applications, Interviews & Offers boundaries to generate the most off-diagonal mass. If the matrix confirms this, it validates that those two decision-rule boundaries are the hard ones and gives concrete direction for future annotation improvements.

--- 

## Definition of Success

    Good enough for deployment: Fine-tuned model achieves overall accuracy ≥ 65% and per-class F1 ≥ 0.55 for all labels, meaningfully beating the zero-shot baseline by at least 10 percentage points on overall accuracy.
    Strong performance: All per-class F1 scores ≥ 0.70 and overall accuracy ≥ 75%.
    Minimum acceptable: Fine-tuned model outperforms zero-shot baseline on at least 3 of 4 labels.

These thresholds are realistic for a subjective 4-class intent classification task with only 200 training examples. If the fine-tuned model barely beats or underperforms the baseline, that signals a label quality or annotation consistency issue worth investigating.

---

## AI Tool Plan

**Label stress-testing:**

I will provide Gemini 3.1 Pro and Claude Sonnet 4.6 with my csMajors taxonomy, and ask them to generate 5-10 posts that sit at the boundary between two or more labels. If I can't classify these cleanly using my definitions, I'll tighten the definitions before committing to annotation.

**Annotation assistance:**

I will use an LLM to pre-label a batch of examples before reviewing them myself, I will likely use two AI tools for the best possible labeling. I will use Gemini 3.1 Pro as well as Claude Haiku 4.5. I will have two different columns to record both of their labels and then a final column with my label. 

I will be providing my exact label definitions and asking Claude and Gemini to generate a CSV file assigning one label per post. I will then manually review and correct every pre-assigned label. I will document any posts that conflict and add notes disclosing this workflow in the AI Usage section of the README as well as the conflicting posts.


**Failure analysis:**


With the post that create conflict with both Gemini, Claude, and my own labeling. I will use Claude Opus 4.8 to identify patterns which appear in these post to write up an evaluation report and I will verify these patterns by re-reading the examples and seeing if those patterns exist.