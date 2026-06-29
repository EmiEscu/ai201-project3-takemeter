# TakeMeter: r/csMajors Intent Classification Project

## DEMO VIDEO: https://youtu.be/eS2BjTkq07E


### Community Selection
I chose `r/csMajors` as the target community for this classification task. I selected this subreddit because it is highly text-centric, and the stakes for the users are extremely high (careers, degrees, and salaries). Consequently, the discourse naturally segments into very distinct, functional buckets. Furthermore, as a CS major myself, I am deeply familiar with the domain-specific jargon (e.g., "TC", "McFAANG", "OA", "LC"), which allowed me to design highly accurate label boundaries and spot when users were using "stealth flexes" disguised as questions.

---

### Taxonomy & Label Design
I designed a 4-label taxonomy based on the psychological intent and chronological pipeline state of the author:

1. **Label 1: Venting & Commentary:** Expressive broadcasts, debates, and commiseration (e.g., "Tech culture is terrible").

**Ex1 (Label 1):**
```

"I just was meeting up with someone I know who is working as a big tech SWE intern. I was telling them about my sister who’s working towards becoming a
trauma surgeon (a type of doctor that treats stuff like vehicle accident or assault injuries, etc). His first reaction was: “why doesnt she js go into
tech for the TC? med school lwk expensive. its ezier js to internshipmax and retire early from big tech promos”. . . You’re a HUMAN. You will DIE. On 
your deathbed, are you really going to fucking be thinking about the shitty levels.fyi salary page?! Or are you going to be desperately pleading to that
trauma surgeon to do anything they can so that you can live to see the sunset another day. Just think about that. FUCKKKKK" 
[https://www.reddit.com/r/csMajors/comments/1udruwf/genuine_crash_out/]

```

**Ex2 (Label 1):**

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


2. **Label 2: Skills & Study:** Optimizing for the future without a live event (e.g., "What certs do I need for IT?").

**Ex1 (Label 2):**

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


**Ex2 (Label 2):**

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

3. **Label 3: Applications, Interviews & Offers:** Navigating an active, scheduled hiring pipeline event.

**Ex1 (Label 3):**

```
"I currently have two offers:      IBM in the middle of no where (Junior Cloud position)      Small company (around 400 employees) in Pittsburgh area. (Software Test Engineer)  I know there is a debate in the career paths themselves, but I’m currently debating if the resume value of IBM brings more opportunity or being located in a decent tech hub does. These positions are very similar in pay.  I would prefer to move into SWE, but prefer the Cloud position over the Test Engineer position. I believe the test position would give me a path to SWE whereas the Cloud position would likely not. Overall, for this debate I am unsure which position brings me better career trajectory overall."
[https://www.reddit.com/r/csMajors/comments/1uel4gn/big_name_bad_location_vs_small_name_good_location/]

```

**Ex2 (Label 3):**

```
"Hi, I am a CS major who graduated this past December. After about 5 months of applying and interviewing, I was able to secure two offers. I am extremely grateful, as I was honestly getting so tired of the job hunt; this was a massive break for me. However, I now have a dilemma regarding which offer to accept.  I have a lot of people in my ear telling me that IBM will look incredible on my resume, and that I should drop everything to go there. Any advice would be great. Everyone in my life is pushing me to choose IBM and practically calling me dumb if I don't pick IBM, but I honestly don't know if a company's name carries that much weight on a resume anymore.  Fortune 500 Company  Position: SWE (Atlanta)  76.5k + 5% Bonus of salary given at end of year every year  Pros:  - Will not have to relocate can live at home with parents (save) and if I wanted to move out rent is affordable.  - Know my manager and the team. Vibes are great.  - Big emphasis on Work Life Balance by the manager  - Hybrid 2 days in office, but is flexibility and could be less.  - Start date is soon  Cons:  - Not a big tech name like IBM  IBM  Position: Data Engineer Future Now CIC (Chicago)  85k + 3k sign on bonus  Pros:  - Big tech name  - Better Salary  - Living and exploring a whole new city  Cons:  - Not SWE, but data engineer title  - Almost 2k in rent in Chicago for a studio  - I do not know my team or manager.  - Start date is not for awhile  UPDATE: Thank you everybody for the advice I really needed it and appreciate it! I am going with offer 1 with the Fortune500 as I like the WLB, the team, manager and the work I would be doing. The work is full range of a lot of things backend infrastructure , digital marketing, data pipelines, ai agents and a lil bit of consulting. So I feel I would be able to learn a lot and pivot if I ever want to in the future. As before thank you again to everybody!"
[https://www.reddit.com/r/csMajors/comments/1u9h5cn/offer_dilemma/]
```


4. **Label 4: Internship & Workplace Situations:** Navigating dynamics *inside* an active, accepted role.

**Ex1 (Label 4):**

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

**Ex2 (Label 4):**

```
Was extremely lucky to get a faang+ swe internship and a return offer. What’s the best path to ensure job security? Stay at the company for as long as 
possible, or build up my resume? What’s the safest route?
[https://www.reddit.com/r/csMajors/comments/1uac9kg/broke_into_faang_now_what/]

```


**Design Decision:** I utilized a strict, top-down "Cascade Rule" for classification. The #1 source of mislabeling in this domain is a vent disguised as a question (e.g., "Am I cooked?"). By forcing the classifier (and myself) to evaluate Step 1 ("Is this a permission-seeking broadcast?") *before* looking for keywords like "interview" or "internship," I prevented emotional rants from bleeding into the advice/study categories.

---

## Data Collection & Annotation
**Data Source:** 200 Reddit posts manually scraped from `r/csMajors` via the Hot, Rising, New, and Top feeds, plus the Project Showcase Megathread. Posts were downloaded as raw JSON and assembled into a structured CSV.

**Labeling Process:**
1. The full label taxonomy from `planning.md` was provided to both **Gemini 3.1 Pro** and **Claude Haiku 4.5**, prompting each to pre-label all 200 posts independently, producing two parallel label columns.
2. Every pre-assigned label was manually reviewed against the top-down cascade rules, correcting disagreements on the spot.
3. Posts where the two models disagreed — or where I overrode both — were flagged, re-read, and resolved by re-applying the cascade. All final labels represent my own human ground truth.

**Dataset:** [`data/r_csMajors data Labeled - Labeled Data.csv`](data/r_csMajors%20data%20Labeled%20-%20Labeled%20Data.csv)

- **Total Annotated Examples:** 200 posts
- **Label Distribution:**

| Label | Count | % of Dataset |
|-------|-------|--------------|
| Venting & Commentary | 61 | 30.5% |
| Skills & Study | 76 | 38.0% |
| Applications, Interviews & Offers | 49 | 24.5% |
| Internship & Workplace Situations | 14 | 7.0% |
| **Total** | **200** | **100%** |

> **Note:** `planning.md` targeted Label 3 (Applications, Interviews & Offers) at ~35%, but the final dataset landed at 24.5% (49 examples). Label 1 (Venting & Commentary) ran higher than anticipated at 30.5% — r/csMajors generates substantially more expressive content than expected, particularly during peak recruiting season.

---

### Hard Edge Cases & Decisions

| Post | Title (short) | Looks like | Label | Why |
|---|---|---|---|---|
| [https://www.reddit.com/r/csMajors/comments/1udwoe4/can_i_just_quit_my_internship/] | Can I just quit my internship | 4 | **1** | Plan already detailed; "anything stop me?" is permission-seeking, not a real ask |
| [https://www.reddit.com/r/csMajors/comments/1uac9kg/broke_into_faang_now_what/] | Broke into faang, now what? | 3 | **4** | Return offer accepted → strategy from *inside* an accepted role |
| [https://www.reddit.com/r/csMajors/comments/1ubbqxm/how_much_does_faang_move_the_bar/] | How much does FAANG move the bar? | 3 | **2** | No live process event; it's about general competitiveness/profile value |
| [https://www.reddit.com/r/csMajors/comments/1ubw97s/amazon_fall_internship_delays_grad_1_semester_vs/] | Amazon internship vs stay on current track | 4 | **3** | Currently interning, but the live decision is whether to *accept another offer* |
| [https://www.reddit.com/r/csMajors/comments/1u9pe4b/new_grad_job_search_is_seriously_affecting_my/] | New grad mental health / how are you dealing | 1 | **2** | Leads emotional but pivots to "what actually worked" — asks for tactics |
| [https://www.reddit.com/r/csMajors/comments/1ueufjs/who_to_believe/] | Who to believe (AI coding) | 2 | **1** | Identity/opinion discussion, not a concrete learning request |
| [https://www.reddit.com/r/csMajors/comments/1uambba/cs_new_grad_looking_for_advice_about_job/] | CS New Grad looking for advice about job | 3 | **4** | Already accepted, starts in a week → tenure/in-role question |

---

## Fine-Tuning Pipeline
The model is fine-tuned from **`distilbert-base-uncased`**, executed in a **Google Colab T4 GPU** environment using the `transformers` library. 
- **Hyperparameter Decisions:** 
  - `num_train_epochs = 12`: Increased from the default 5 after early runs showed underfitting — validation loss was still improving at epoch 5, and the minority Label 4 class had not yet converged.
  - `metric_for_best_model="eval_f1"` (macro): Originally set to `eval_accuracy`, but switched mid-training after observing the model was inflating its score by defaulting to the two majority classes (Labels 2 and 3) while ignoring Label 4 entirely. Macro F1 penalizes this by averaging performance equally across all four classes regardless of support size.
  - `per_device_train_batch_size = 16`: Chosen to fit comfortably within the T4 GPU memory limits without causing OOM errors.
  - `warmup_ratio = 0.1`: Replaced a hardcoded `warmup_steps = 50`, which exceeded the per-epoch step count (45 steps), starving the model of a working learning rate before training ended. Switching to a ratio guaranteed warmup scaled with the actual training length.


## Baseline Description
For the one-shot per class baseline, we prompted Groq's `llama-3.3-70b-versatile`. We used a system prompt that explicitly named the 4 labels, provided the definitions (straight from our planning), and included one example per label. The LLM was strictly instructed to output *only* the label name.

---

## Evaluation Report Summary

| Model | Overall Accuracy | Macro F1 |
|-------|-----------------|----------|
| Zero-Shot Baseline (Llama-3.3-70b) | **80.0%** | 0.73 |
| Fine-Tuned DistilBERT (12 epochs) | 63.3% | 0.56 |

The zero-shot baseline outperforms the fine-tuned model by **16.7 percentage points** on overall accuracy. The fine-tuned model's primary failure mode is Label 4 (Internship & Workplace Situations, F1: 0.29), which was severely underrepresented at 7.0% of the training data (14 examples). The baseline's best class is Label 3 (F1: 0.93); the fine-tuned model's best class is Label 2 (F1: 0.77). Three specific failure patterns — the Rhetorical Question Trap, the Live Event Hallucination, and the Topic vs. Context Failure — are documented in the Error Analysis section below.

---

## Baseline Results (One-Shot Per Class Prompt)
🎯 Baseline accuracy: 0.800  (evaluated on 30/30 parseable responses)

Per-class metrics (baseline):
|label    | precision |  recall | f1-score | support |
|-------- |---------- | ------- | -------- | ------- |
| Venting & Commentary |                   0.75 | 0.67 | 0.71 | 9 |
| Skills & Study |                         0.91 | 0.83 | 0.87 | 12|
| Applications, Interviews & Offers |      0.88 | 1.00 | 0.93 | 7 |
| Internship & Workplace Situations |      0.33 | 0.50 | 0.40 | 2 |
|
| accuracy           |           |          |      0.80|        30|
| macro avg          |       0.72|      0.75|      0.73|        30|
| weighted avg       |       0.82|      0.80|      0.80|        30|

**Where the baseline struggled**

The model experienced severe difficulty classifying Internship & Workplace Situations.

- Low Precision (0.33): The model predicted this category three times, but was only correct once. This means two-thirds of the posts it labeled as "Internship & Workplace Situations" actually belonged to another category (high false-positive rate).

- Low Recall (0.50): Out of the two actual posts belonging to this category, it only successfully identified one.

- Venting & Commentary (F1-Score: 0.71): The model also showed moderate weakness here. A recall of 0.67 indicates that it missed 3 out of the 9 actual venting posts (false negatives), likely categorizing them as genuine advice requests.

**Confusion & Hypothesis Baseline**
By reverse-engineering the metrics (Total = 30; True Positives = 24), the specific confusion patterns become clear:

- Hypothesis 1: Keyword Over-indexing on "Internship"
    Because the model generated multiple false positives for Internship & Workplace Situations (a precision of 0.33), it is likely seeing the word "internship" in posts that are actually general study questions (Label 2) or vents (Label 1) and incorrectly classifying them as Label 4, failing to recognize that the author hasn't actually started the job yet.

- Hypothesis 2: The Rhetorical Question Trap
    Venting & Commentary generated 3 false negatives. The baseline model is likely misclassifying emotional rants as Skills & Study (Label 2) or Applications, Interviews & Offers (Label 3) because it cannot distinguish between a rhetorical, permission-seeking question ("Am I cooked?") and a genuine request for a career roadmap.

- Hypothesis 3: Severe Class Imbalance (Underrepresentation of Label 4)
    With Internship & Workplace Situations making up only ~7% of the dataset (a support of 2 out of 30), the model is suffering from extreme class imbalance. The baseline simply did not have enough data or exposure to this specific category to learn its defining characteristics and nuanced boundaries, making it unable to reliably differentiate Label 4 from the more dominant classes.

---

## Fine Tuned Results (12 Epochs)

🎯 Fine-tuned model accuracy: 0.633

Per-class metrics (fine-tuned model):

| label   |precision  | recall  | f1-score | support |
|-------- |---------- | ------- | -------- | ------- |
| Venting & Commentary | 1.00 | 0.33 | 0.50 | 9 |
| Skills & Study | 0.71 | 0.83 | 0.77 | 12|
| Applications, Interviews & Offers | 0.62 | 0.71 | 0.67 | 7|
| Internship & Workplace Situations | 0.20 | 0.50 | 0.29 | 2|
|
|          accuracy |       |              |     0.63 |       30|
|         macro avg |      0.63 |     0.60 |     0.56 |       30|
|      weighted avg |      0.74 |     0.63 |     0.63 |       30|



---

### Confusion Matrix

Fine-Tuned Model - Confusion Matrix (Test Set)

| | **Venting & Commentary** | **Skills & Study** | **Application, Interviews & Offers** | **Internship & Workplace Situations** |
|-----------|----------------|--------------------|---------|------------|
| **Venting & Commentary** | 3 | 2 | 2 | 2 |
| **Skills & Study** | 0 | 11 | 1 | 1 |
| **Application, Interviews & Offers** | 0 | 1 | 5 | 1 |
| **Internship & Workplace Situations** | 0 | 1 | 0 | 1 |
 

(Predicted label are in the columns, true labels are in the rows)
<br />


---

### Error Analysis (3 Wrong Prediction)

1. 
    Text: "Don't want to specify which one, but I'm super excited to finally be working at a top tier McFAANG company! I will be in a Forward Deployed Food Engineering Specialist role! Some of my job responsib..."
    True:      Venting & Commentary
    Predicted: Internship & Workplace Situations  (confidence: 0.98)
    Analysis: The model over-indexed on workplace vocabulary like "working at a top tier company," "job responsibilities," and "Specialist role." It failed to recognize the satirical tone (McFAANG, Food Engineering = working at McDonald's).


2. 
    Text: "Graduating this July and stuck on a decision. I have a grad offer on the table but it's not in London (2hr daily commute), pay is meh, and it's not really where I want to be. The only reason I was co..."
    True:      Applications, Interviews & Offers
    Predicted: Internship & Workplace Situations  (confidence: 0.99)
    Analysis: The model saw phrases about working conditions ("2hr daily commute", "pay is meh") and confidently assumed the author was already navigating a workplace situation.

3. 
    Text: "In a toxic team and I’m thinking of changing companies or teams. I’m thinking change teams first so that at least my mental health is no longer getting bad and wondering how long to wait before I can ..."
    True:      Internship & Workplace Situations
    Predicted: Skills & Study  (confidence: 1.00)
    Analysis: The model latched onto the career strategy aspect of the question ("thinking of changing companies," "wondering how long to wait before I can [apply]"). It saw a question about job-hopping strategy and defaulted to Skills & Study.

---

### Sample Classifications Table

The table below serves as the model classification source — showing the fine-tuned DistilBERT model processing 4 live posts with predicted labels and confidence scores. Two correct and two incorrect predictions are included, with one correct prediction explained in full.

| Post Excerpt | True Label | Predicted Label | Confidence | Reason |
|--------------|------------|-----------------|------------|--------|
| *"Hi I just finished the first year of my CS degree (of a 4 year program). I do not have an internship for this summer but I thought I would take this opportunity to build skills+ projects and explore ..."* | `Skills & Study` | `Skills & Study` | 1.00 | **Correct Prediction:** The model successfully identified this as a general academic and career preparation post. The author is seeking a learning roadmap and project ideas without being anchored to any active job pipeline or current role, perfectly matching the positive definition for Label 2. |
| *"About how many people got the mail for 15 minute hr round from big code?and how many will advance to the technical rounds any idea??"* | `Applications, Interviews & Offers` | `Applications, Interviews & Offers` | 1.00 | **Correct Prediction:** The model accurately detected the "live event" trigger. The author is asking about conversion rates for an active, specific hiring pipeline ("15 minute hr round from big code"), satisfying the strict boundary rule for Label 3. |
| *"I currently have two offers:      IBM in the middle of no where (Junior Cloud position)      Small company (around 400 employees) in Pittsburgh area. (Software Test Engineer)  I know there is a debat..."* | `Applications, Interviews & Offers` | `Skills & Study` | 0.58 | **Incorrect:** The model failed because it over-indexed on the career strategy aspect of the post (debating between Cloud and Test Engineering). It missed the critical boundary rule that having live "offers on the table" instantly anchors the post to the hiring pipeline, overriding the general career discussion and requiring Label 3.|
| *"Hi all, I’m a systems engineer with most focus on linux and DevOps practices. I passed the initial phone screen where they asked deep linux questions. Now I have a second round which is coding in py..."* | `Applications, Interviews & Offers` | `Skills & Study` | 0.62 | **Incorrect:** The model hallucinated a Label 2 prediction by focusing on technical keywords like "linux", "DevOps", and "coding" as if it were a general study question. It completely ignored the explicit "live event" context—the author has passed a phone screen and is actively preparing for a scheduled second-round interview, which mandates Label 3.  |

---


## Which labels are being confused? 

Looking at the confusion matrix, there are three major directional patterns accounting for the vast majority of the errors:
1. **The Rhetorical Question Trap:** The model consistently confuses *Venting & Commentary* (Label 1) for *Skills & Study* (Label 2) when a post ends with an unanswerable or permission-seeking question (e.g., "Am I cooked?"). 
2. **The Live Event Hallucination:** The model confuses *Skills & Study* (Label 2) for *Applications, Interviews & Offers* (Label 3) by over-indexing on keywords like "resume," "interview," or "offer," failing to realize the user is asking a general prep question rather than navigating a live hiring event.
3. **The Topic vs. Context Failure:** The model consistently misclassifies *Internship & Workplace Situations* (Label 4) by predicting Label 2 or Label 3. It fails to recognize the "Hierarchy of State" boundary rule—that a user navigating life *inside* an active role overrides the subject matter of their question.

## Why is that boundary hard? 

These boundaries are hard because the topic signals one label but the intent/context signals another:
* **Label 1 vs. Label 2:** The boundary is obscured by the structure of the posts. Users in `r/csMajors` frequently disguise deeply emotional vents as advice-seeking questions ("Has anyone else struggled with this, if so how did you overcome it?"). The model's literal interpretation of question marks overrides its ability to detect the actual intent of commiseration or sarcasm.
* **Label 2 vs. Label 3:** The boundary is hard because of shared vocabulary. The language used to ask "How should I study for technical interviews?" (Label 2) is nearly identical to "I have a technical interview tomorrow, how do I pass?" (Label 3), but the pipeline state (theoretical vs. live event) is completely different.

## Is this a labeling problem or a prompt/data problem?

This is fundamentally a **prompt and data problem**, not an annotation inconsistency problem. I labeled the examples consistently according to the top-down cascade rules defined in `planning.md`. The model failed for two distinct reasons:
1. **Data Imbalance (Label 4):** *Internship & Workplace Situations* only represented 7.0% of the dataset. The model severely underfit to this class because it didn't have enough exposure to learn the nuanced boundary rules, leading it to guess majority classes instead.
2. **Prompt/Boundary Enforcement (Labels 1, 2, and 3):** The model relied entirely on basic keyword matching rather than the "intent and state" logic I designed. The original prompt did not explicitly warn the model against the "Rhetorical Question Trap" or define the strict difference between a live event and general prep. 

## What would need to change to fix it? 

To fix the model's accuracy, a multi-pronged approach addressing both the prompt and the training data is required:

1. **Prompt Bulletproofing (Tighter Definitions):** The system prompt needs explicit "anti-keyword" instructions. 
   * **For Label 1:** Add a rule stating, "You must ignore rhetorical question marks (e.g., 'Am I cooked?') and evaluate if actionable advice can actually be given."
   * **For Label 3:** Add a rule stating the post MUST be anchored to a "currently active, named, or scheduled" point in the hiring pipeline.
   * **For Label 4:** Add a "Hierarchy of State" rule stating that being actively employed overrides the technical subject of the post.
2. **Data Balancing & Fine-Tuning Strategy:** * Do **not** merge Label 4 into Label 3. The psychological intent and advice required for an active employee versus an applicant are entirely different. 
   * Instead, we must collect more diverse, explicit examples of Label 4 (e.g., by mining "Internship" megathreads).
   * Finally, update the fine-tuning script to use a custom `WeightedTrainer` with PyTorch class weights to heavily penalize the model for missing the minority classes, while bumping the training length to 15 epochs to ensure convergence without underfitting.





### Reflection on Model Collapse (Error Pattern Analysis)

I designed a taxonomy based on the psychological intent and chronological state of the user. The model built a decision boundary based almost entirely on vocabulary buckets. To fix this, the prompt needs explicit anti-keyword instructions, and the fine-tuning process requires heavy class weighting to force the model to respect the minority categories. I also need to get more data to even out under represented labels for better training. 



## Specification Reflection

**How the spec helped guide my implementation:**
The requirement to define strict "Positive", "Negative", and "Boundary" definitions in my `planning.md` file was crucial. It forced me to implement the "Remove the Replies" tiebreaker test. Whenever I was stuck on a post (like a user complaining about failing a class but asking "what's stopping me from dropping out?"), the spec forced me to ask: *If no one replies, does this post still serve its purpose?* Since the answer was yes—the user just wanted to vent and broadcast their frustration—it clearly guided me to map the post to Label 1 instead of Label 2, keeping my annotations consistent.

**How my implementation diverged from the spec and why:**
My original spec and modeling plan assumed that standard fine-tuning hyperparameter defaults (e.g., 5 epochs, 50 warmup steps, optimizing for accuracy) would be sufficient for a 200-example dataset. However, in practice, I had to completely diverge from this. 

During early fine-tuning, I experienced a severe regression (-26.7% vs. the zero-shot baseline). My model's validation loss was dropping, but training halted abruptly. Furthermore, my dataset was highly imbalanced (Label 4 was only 7.5% of the data), meaning the model was simply guessing the majority classes to inflate accuracy. I diverged from my `metric_for_best_model` to `f1` (macro), switched from static warmup steps to a `warmup_ratio=0.1`, and bumped training to 12 epochs to ensure the underrepresented classes were actually learned.

---

## AI Usage & Disclosures

Throughout this project, I used AI tools strategically for data annotation, debugging, and metric analysis.

**Instance 1: Pre-Labeling & Annotation Assistance**
* **Direction:** I provided my `planning.md` taxonomy to both Gemini 3.1 Pro and Claude Haiku 4.5, prompting them to pre-label my dataset of 200 scraped posts. I asked them to generate a CSV comparing their predictions.
* **Output:** The LLMs generated a CSV with their respective labels. However, upon manual review, I realized Claude only achieved a ~54.5% accuracy against my final human labels. Claude fell into what I called the "Rhetorical Question Trap" (labeling highly emotional vents ending in a question mark as Label 2) and the "Live Event Hallucination" (keyword-matching the word "interview" and defaulting to Label 3).
* **Changes/Overrides:** I manually overrode 94 disagreements to establish the final human ground truth. Based on this AI failure, I completely rewrote my `SYSTEM_PROMPT`. I explicitly added instructions banning keyword matching and added "LLM Prompting Rules" to the taxonomy, forcing the downstream model to ignore rhetorical question marks and prioritize the pipeline state of the author.

**Instance 2: Baseline Script Debugging and Regression Analysis**
* **Direction:** While running my zero-shot baseline script using the Groq API (Llama-3.3-70b), my evaluation script returned 30/30 `None` unparsed labels. Later, after my first fine-tuning run, my accuracy stalled at 53.3%. I fed the script and screenshots of my Weights & Biases terminal logs to an AI assistant, asking it to diagnose the baseline parsing failure and explain the fine-tuning regression.
* **Output:** For the parsing script, the AI identified a case-sensitivity bug: I was lowercasing the raw output (`raw.lower()`) but checking if it matched capitalized strings in my `LABEL_MAP`. For the fine-tuning, it analyzed my terminal output and correctly diagnosed underfitting. It pointed out that my 50 `warmup_steps` exceeded my total training steps (45), starving the model of a learning rate before the 5 epochs finished.
* **Changes/Overrides:** I rewrote the baseline parser to lowercase the target labels dynamically during the loop (`target = label.lower()`). For the fine-tuning pipeline, I adopted the AI's structural recommendations: dropping the hardcoded warmup steps for a `warmup_ratio`, increasing the epochs, and incorporating the custom class-weighted loss function.






