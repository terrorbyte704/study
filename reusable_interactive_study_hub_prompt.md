# Master Prompt: Zero-to-100 Interactive Study Hub & Midterm Mastery Builder (No Gamification)

Copy and paste the prompt below into any AI assistant alongside your lecture slides/PDFs (and any past quizzes or midterm exams):

```
You are an expert University Professor and Interactive Educational Web App Architect.

I am uploading my course lecture slides/PDFs (and, if attached, past quizzes/midterm exams). Build a complete, single-file HTML study application (`study_hub.html`) that teaches the entire material from **0 to 100** simply, clearly, and comprehensively so I can walk into the midterm/exam and score an A+.

### MANDATORY 4-PHASE EXECUTION WORKFLOW (DO NOT SKIP OR SUMMARIZE SLIDES!)

Why AI assistants normally fail at 0-to-100 study guides: AI models tend to group a 40-page PDF into 3 high-level themes and write a compressed summary from memory (dropping individual slides), and then write quiz questions separately from general textbook knowledge—causing questions to test concepts that were skipped in the lesson! To prevent this, you MUST execute in this exact order:

- **Phase 1 (Page-by-Page Slide Inventory):** Extract the text of every single page (`Page 1..N`) of every uploaded PDF first. Build a complete checklist of every technical slide's concepts, definitions, tables, formulas, and code examples (excluding only syllabus/grading fluff).
- **Phase 2 (Write Full 0-to-100 Sub-Lessons Mapped to Every Slide):** Assign every technical slide from Phase 1 to a specific Sub-Lesson (`1.1`, `1.2`, ...). Write the Sub-Lessons in modular data files/chunks (never squeeze all lectures into one tiny summarized script!) so that **100% of the slides are taught in full depth from 0 to 100**.
- **Phase 3 (Generate Quizzes Directly From the Written Sub-Lesson HTML):** Write each Sub-Lesson's 3 Concept Check questions and each Lecture's Mastery Exam *strictly from the text written in Phase 2*—never from outside general knowledge and never placing a concept from Sub-Lesson B inside Sub-Lesson A's quiz.
- **Phase 4 (Automated Verification Script Before Delivering):** Run a script to verify that: (1) every quiz question's tested term appears in its exact Sub-Lesson HTML, (2) all 4 options (`A, B, C, D`) are within 5–15 characters in length (`~25%` longest) with even `A/B/C/D` answer distribution (`~25%` each), and (3) 100% of `$ ... $` LaTeX blocks have balanced `{}` braces.

### STRICT UI, ANIMATION, VISUAL & PEDAGOGICAL RULES (NON-NEGOTIABLE)

1. **100% SLIDE-BY-SLIDE COVERAGE & STRICT SUB-LESSON-TO-MCQ ALIGNMENT (ZERO MISSING CONCEPTS):**
   - Start every Sub-Lesson with a **"💡 Plain-English Intuition / Big Picture"** callout box that explains *why* the concept exists and *how* to picture it using everyday analogies before introducing formal equations or code.
   - Audit every page of every uploaded PDF slide deck so **zero technical concepts, definitions, formulas, or code examples are skipped**.
   - **Strict Sub-Lesson-to-MCQ Alignment Rule:** Every single question in a Sub-Lesson's right-side Concept Check (and every question in a Lecture's Mastery Exam) MUST strictly test concepts that are **explicitly taught and explained inside that exact Sub-Lesson (or Lecture)**. Never ask a question about a term (e.g., NUMA, SPMD, `atomic`, `single` vs `master`, `collapse`) unless that exact concept is thoroughly explained in the sub-lesson text right beside it, and never include out-of-syllabus trivia not present in the slides.
   - Whenever a topic is split across two slide decks (e.g., "Part A & Part B" or "Part 1 & Part 2"), combine them into a single unified Lecture module containing all sub-lessons, quizzes, and review tables in one place.

2. **STRICT VISUAL & IMAGE QUALITY RULE (NO TEXT-SLIDE SCREENSHOTS!):**
   - **NEVER** crop or embed screenshots of text-only slides, bullet-point lists, title slides, or code slides as images! If a slide is text, code, or a table, convert it into clean, searchable HTML text, `<pre><code>` blocks, or `<table>` matrices.
   - **ONLY include images when they are genuine visual diagrams, hardware architecture blocks, data graphs/plots, chip die photos, or Directed Acyclic Graphs (DAGs).**
   - When cropping a diagram from an uploaded PDF, verify that the page actually contains a visual figure (`imgs >= 1`) and crop tightly around the visual diagram itself (excluding surrounding slide bullet text). Where a concept needs a visual diagram that isn't a clean image in the slides (e.g., bus architectures, timelines, or memory flowcharts), draw a crisp, dark-mode-native inline `<svg>` diagram.

3. **DEFAULT DARK THEME & FULL-WIDTH WIDESCREEN LAYOUT (NO WASTED EMPTY SPACE):**
   - Default to a sleek **Dark Theme** (`<html lang="en" class="dark">`, deep slate `#080c16` / `#11182d` cards with emerald/cyan accents and a Light/Dark toggle `🌗`).
   - Use the **full width of the screen** (`w-full px-4 sm:px-6 lg:px-8`)—never constrain the page to a narrow centered column with huge empty margins on the sides.

4. **TEMPORARY FLOATING OVERLAY DRAWERS FOR LECTURES & TOOLBAR (UNLESS TOOLBAR IS PINNED):**
   - **Top Header Bar (Row 1 — Single Clean Row, No Duplicate Mode Pills!):**
     - **Left:** ONE unified `☰ 📚 Lectures (1–N) ▾` button + `🧭 Toolbar: [Current Section] ▾` button + Course Title.
     - **Center:** Instant Global Search input (`🔍 Search concepts, formulas, code, exam questions...`) that displays live clickable search results across all lessons and question banks.
     - **Right:** **Completion Progress Bar** (`Progress: X% (Y/Z)`) + Flagged Questions counter (`🚩 0`) + Theme toggle (`🌗`) + `Reset` button. (Do **NOT** put duplicate quick-jump pills for `Past Midterm`, `Coding Lab`, or `Review Hub` in Row 1—keep all mode buttons hidden inside the `🧭 Toolbar` drawer so Row 1 stays compact!)
   - **Temporary Floating Lectures Drawer (`fixed top-14 left-4 sm:left-6 lg:left-8 z-50 shadow-2xl`, Closed by Default):**
     - When `☰ 📚 Lectures (1–N) ▾` is clicked, the Lectures drawer MUST appear **temporarily floating on top of the existing page** (`fixed` overlay) instead of pushing or shrinking the page sideways!
     - Selecting a sub-lesson or clicking outside the drawer automatically closes the floating Lectures drawer.
   - **Mode Toolbar (`#modeToolbarDrawer`, Closed by Default, with `Keep Toolbar Pinned` checkbox):**
     - Put all major application sections exclusively inside this toolbar (`📖 1. 0-to-100 Lessons & Inline Labs`, `🔥 2. Past Midterm & Similar Qs`, `💻 3. Coding Practice Lab`, `📋 4. Synthesis Review Tables`, `🖼️ 5. All Verified Diagrams (.png)`, `🎯 6. Full Practice Exam Simulator`).
     - **When Unpinned (`pinToolbar: false`, default):** Opening `🧭 Toolbar` makes the toolbar appear **temporarily floating on top of the existing page** (`absolute left-0 right-0 top-full z-50 shadow-2xl`) without pushing the page downward; selecting a mode or clicking outside automatically dismisses it.
     - **When Pinned (`pinToolbar: true`, when `Keep Toolbar Pinned` is checked):** The toolbar switches from `absolute` to `relative` (in-flow inside the sticky `<header>`), **moving the page downward to make room** and staying docked open.

5. **SMOOTH UI ANIMATIONS ON EVERY INTERACTION:**
   - Include CSS `@keyframes` and JS animation triggers (`animateCollapsible` + `lastNavAnim`) for:
     - **Sidebar Slide-In / Slide-Out** (`sidebarSlideIn` / `sidebarSlideOut`, `translate3d(-24px, 0, 0)`) when toggling `Lectures (1–N)`.
     - **Top Mode Toolbar & Search Drawer Slide-Down / Slide-Up** (`drawerSlideDown` / `drawerSlideUp`, `scaleY(0.95) translate3d(0, -10px, 0)`).
     - **Sub-Lesson Next / Previous Slide Transitions** (`lessonSlideNext` / `lessonSlidePrev`, `translate3d(±28px, 0, 0)`) when stepping between sub-lessons.
     - **Chapter Fade-Up & Mode Tab Fade-In** (`chapterFadeUp` / `viewFadeIn`) when switching lectures or main tabs.
     - **Right-Side Companion Panel Slide-In** (`companionSlideIn`, `translate3d(24px, 0, 0)`) and **Quiz Explanation / Simulator Metric Pop-In** (`answerPopIn`), plus `<details open> > div` accordion animations and `active:scale-95` button micro-interactions.

6. **2-COLUMN SUB-LESSON VIEW, RIGHT-SIDE CONCEPT CHECK & SINGLE-CLICK "MARK COMPLETE & NEXT LESSON" BUTTON:**
   - Inside each Lecture, make every Sub-Lesson section expandable/collapsible (`<details open>`) and include an **"Expand All Sections in Lecture"** button.
   - Use a responsive 12-column split inside each sub-lesson:
     - **Left Main Column (`xl:col-span-7 2xl:col-span-8`):** The 0-to-100 sub-lesson explanation, mathematical derivations, comparison tables, verified diagrams, and (where needed) the inline interactive simulator.
     - **Right Sticky Side Column (`xl:col-span-5 2xl:col-span-4 xl:sticky xl:top-24`):** Place the **Sub-Lesson Concept Check (3 Atomic Questions)** right on the side beside the lesson (with a toggle to hide/show the side panel).
   - At the bottom of every Sub-Lesson, include a prominent **single-click primary button (`✅ Mark Complete & Next Lesson →`**, or **`🎯 Mark Complete & Go to Lecture X Mastery Exam →`** on the last sub-lesson) that both marks the current sub-lesson completed and immediately advances to the next sub-lesson in one click (alongside `← Prev` and a secondary `✓ Mark Complete Only / Undo` toggle).

7. **END-OF-LECTURE COMPREHENSIVE MASTERY EXAM ON ITS OWN PAGE (NEVER AT THE BOTTOM OF A CHAPTER):**
   - Do **not** dump the End-of-Lecture Comprehensive Mastery Exam at the bottom of the chapter or sub-lesson.
   - Give the **End-of-Lecture Comprehensive Mastery Exam** its own dedicated button/tab in the lecture's sub-navigation bar (`🎯 End-of-Lecture X Mastery Exam — Own Page`) so clicking it opens a dedicated full-width assessment page for that lecture.

8. **ZERO GAMIFICATION & ZERO SYLLABUS FLUFF:**
   - Do NOT include XP, levels, ranks, streaks, badges, or game jargon.
   - Never include course administration, grading policy, attendance rules, or project rubrics. Focus 100% on testable technical content.

9. **PAST MIDTERM BANK + SIMILAR TWIN QUESTIONS, STRICT OPTION-LENGTH & POSITION BALANCING, CLICK-TO-UNDO & PER-OPTION EXPLANATIONS:**
   - Include all official past midterm/quiz questions verbatim (MCQs, True/False, code output traces, and descriptive/DAG math) plus brand-new **Similar Midterm Twin Questions**.
   - Keep sub-lesson checks (3 atomic questions on the right side) and End-of-Lecture Mastery Exams 100% distinct.
   - **Strict Option-Length & Answer-Position Balancing (Never Make the Correct Answer the Longest!):**
     - Across all Sub-Lesson Checks, End-of-Lecture Mastery Exams, and Similar Twin MCQs, write all 4 options (`A`, `B`, `C`, `D`) with **nearly identical character lengths (within 5–15 characters of each other)** and parallel grammatical structure.
     - Never append parenthetical explanations or formula derivations inside the correct option button text (put all explanations inside `optionExplanations`).
     - Audit the final question banks so the correct option is the strictly longest option no more than **~25% of the time** (random chance) and the correct answer index (`0, 1, 2, 3` / `A, B, C, D`) is evenly distributed at **~25% each** (never clustered on Option B).
   - **Unmistakable Question Card Boundaries:** Give every MCQ card a high-contrast **Question Header Bar** (`QUESTION 1`, `QUESTION 2`, plus a live status badge `⚪ Unanswered` / `✅ Answered • Correct` / `❌ Answered • Review Below` and `🚩 Flag`), a thick top accent border (`border-t-4 border-2`) that turns emerald when correct or rose when incorrect, a footer label (`💡 Core Takeaway (End of Question X)`), and generous vertical spacing (`space-y-6`) so it is always obvious where one question ends and the next begins.
   - **Click Same Option to Undo:** On every MCQ, clicking the exact same option that is currently selected must undo/unselect the answer and collapse the explanations so the student can reset that question in one click.
   - **Per-Option Explanations (`optionExplanations` for A, B, C, D):** Every MCQ must provide a dedicated explanation for **every single option** (`✅ Why Option X is Correct:` for the correct choice and `❌ Why Option Y is Wrong:` for each distractor), displayed directly inside each option card once answered alongside the bottom summary takeaway.
   - **Strict LaTeX & JS Escaping Audit:** Verify that every `$ ... $` and `$$ ... $$` LaTeX block has strictly balanced `{` and `}` curly braces and that backslashes inside JS strings/template literals are properly escaped so KaTeX renders 100% of formulas with zero raw `$ ... $` text.
   - Test one single concept per question and use HTML `<strong>`/`<code>` tags instead of raw `**` or `` ` `` in JS strings.
```