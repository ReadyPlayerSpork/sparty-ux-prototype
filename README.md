# Sparty

A group prediction platform for friends and family.

**Live prototype:** https://readyplayerspork.github.io/sparty-ux-prototype/
**Repository:** https://github.com/ReadyPlayerSpork/sparty-ux-prototype
**Author:** Luke Miller

---

## 1. Concept

**Need.** Predictions among friends get made out loud and then forgotten, so nobody can prove they called it.

**Persona.** A person active in a daily group chat, plays and/or watches sports, getting ready for a family reunion, already makes joking predictions out loud a few times a week.

**Capability.** Calling a group prediction and seeing who was right.

**Value.** Validation, connection. Being right stops being something you have to argue for and the people that matter witness it.

---

## 2. The three screens

**Screen 1 — Landing**
*Job:* Signal the capability and the value before the visitor reads anything. A rolling queue of sample predictions sits front and center, each one resolving on screen before the next appears. A two-to-four word thesis sits in the top left, with a highlighted sign-up button and an unhighlighted log-in button below.
*Why it earned a slot:* It gives the user a direct example of what to expect.

**Screen 2 — Home**
*Job:* Show current predictions from the user's groups in a row of cards at the top, and below them the groups they belong to, each showing their place on that group's leaderboard.
*Why it earned a slot:* The two elements together of groups and predictions make the thesis of the app clear immediately after logging in.

**Screen 3 — Group predictions**
*Job:* After opening a group, show that group's predictions as cards (sorted by active then resolved) with emoji reactions, and a leaderboard tab showing each member's points.
*Why it earned a slot:* This is the actual meat of the app, where most of the core capability lives.

> *Changed during the build:* Screen 2's groups were specified as tiled cards and built that way, then converted to full-width rows after review. The reasoning is in the first read below.

---

## 3. Design question plan

Questions to ask the persona later.

**Persona — "How often do you make predictions with your friends, and what does it look like?"**
*Predict:* A few times a week, spoken aloud or dropped in the group chat, clustered around live events and the hours before a gathering. Nobody writes them down.

**Need — "When you make predictions with your friends, what happens after you do?"**
*Predict:* "Nothing." It gets forgotten, or it surfaces only when the person who was right brings it up and then it gets disputed.

**Capability — "I am going to show you the landing page for five seconds. *(Hide it.)* What does this product do?"**
*Predict:* Close to "you make predictions with friends and find out who was right," with groups mentioned.

**Capability — "What would you tap first, and what do you expect will happen?"**
*Predict:* The filled green button over the outlined one. On Home, a Yes or No on the top card before opening a group.

**Value — "What would have to be true for you to use this instead of what you do now?"**
*Predict:* "If my friends were already on it." A distribution answer rather than a value answer.

**Value — "After using it, what is one or two words for what you would get out of this?"**
*Predict:* Validation-family words like "bragging rights," "proof," "being right." Connection words are less likely unprompted.

---

## 4. Design justification and first read

### Does the landing screen signal the capability and value at first glance, before reading?

The capability does. Before reading a word you see a card, a green-and-red split bar, and an outcome stamp. Validation lands once the user has enough time to read the verdict line and points. Connection is the weakest of the three. The member avatars are small and easy to miss at a glance.

### Does every element earn its place, or does anything compete with the primary job?

Most of it holds. The prediction card is the largest element and represents the most important value. The two buttons are below it and deliberately unequal in weight, so nothing competes for the primary action.

The weakest element is the "LIVE IN 1,204 GROUPS" pill in the top-right. It seems unnecessary in hindsight.

### What information and actions belong together, and which Gestalt principle communicates that?

**Landing, common region.** A prediction, its odds bar, and the avatars of who called it sit inside one bordered card. The border is what says where the prediction ends and the page begins, so the two buttons below it read as page-level actions rather than actions on that specific prediction.

**Landing, figure-ground.** When a prediction resolves, the card dims and blurs behind an overlay carrying the YES or NO stamp. The result becomes the figure and the prediction recedes to ground, so attention moves to the outcome without the layout shifting.

**Landing, focal point.** The sign-up button is the only saturated green element in the lower half of the screen, against outlined grey for log-in. Whatever stands out visually gets attention first, so the primary action is established by contrast alone, with no label explaining which button matters more.

**Home, proximity.** "Needs your call" sits directly above its card row with a larger gap below the row than above it. Nearness is what binds the heading to the right content; the gap below is what stops it from also claiming the group list.

**Home, continuity.** The group rows share a left edge and put rank on a consistent right edge, so the eye follows a vertical line down the column and reads rank as a series to compare rather than four separate figures to hunt for.

**Home, similarity, and a deliberate break.** The four group rows share shape, height, and treatment, which is what makes them read as one class of thing. The dashed "Join or create a group" tile breaks that treatment on purpose, so it reads as an action rather than a fifth group.

**Group screen, similarity.** Active and resolved predictions are separated by labelled headings, but the real signal is treatment. Resolved cards are dimmer and lower in contrast, so status is legible as a class before any label is read.

**Across all three, similarity.** The same card shape, border, and corner radius appear on every screen, and the emoji chips are identical on Home and the group screen. This is what makes three screens read as one product rather than three designs.

### Do screens 2 and 3 stay on mission, and can you return to the landing screen from everywhere?

Both show the product working rather than describing it. Home contains a list of predictions and the groups you belong to. The group screen is the same two things narrowed to one group, plus a leaderboard tab.

Every screen returns to the landing screen. The wordmark is a bordered pill button on both Home and the group screen, and the group screen's back control names its destination ("← Groups") rather than showing a bare arrow. (The "Join or create a group" tile has no destination behind it, since group creation was out of scope for three screens.)

### What did the AI get wrong, skip, or oversimplify — and what did you change?

**Navigation.** No direct route from the group screen back to the landing screen, and the wordmark that did return there carried no cue it was tappable. Made it a bordered button present on both screens.

**Improved signaling.** The landing carousel resolved predictions with no warning, so the outcome read as arbitrary rather than anticipated. The active progress dot became a fill bar that completes as the card resolves.

**Value on landing page.** When constructing the landing page, the AI focused only on validation. Connection wasn't presented anywhere on the landing page. Member avatars were added to the landing card and emoji reactions to the Home cards, so the group is visible rather than counted.

**Improved group tiles.** Group tiles were a two-column grid, which gave each group a cell but no shared line to read along. Converted to full-width rows so rank sits on a consistent edge and can be compared down a column, and I instructed the addition of a join or create group button.

### Before and after

**Before:** <img width="2526" height="1688" alt="image" src="https://github.com/user-attachments/assets/f2d79eab-5352-42d1-964c-0885dbc5d969" />

**After:** <img width="2526" height="1832" alt="image" src="https://github.com/user-attachments/assets/93451473-206a-4778-af32-22374188ba57" />

In the grid, comparing standing across groups meant reading four separate boxes. The grid system also made it too similar to the prediction cards. The rows put name on a shared left edge and rank on a shared right edge, so standing and group names reads down a single line and distinguished groups from predictions. The change was made for similarity and continuity, not appearance.

---

