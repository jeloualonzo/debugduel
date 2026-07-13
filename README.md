# 🐞 Debug Duel — Classroom Console

A single-file web app for running the **Debug Duel** classroom activity on one laptop —
no installation, no internet, no extra apps. It replaces the paper lots, the roulette
wheel, the notepad, and the timer in one window you keep side-by-side with NetBeans.

## Run it

Download `index.html` and double-click it (opens in any browser). That's all.

## The activity

Students take turns on the teacher's laptop. Each student picks a level:

| Round | Pick | Time | Correct | Not correct |
|-------|------|------|---------|-------------|
| MAIN  | HARD (H01–H20) | 3:00 | **15 points** | 0 |
| MAIN  | EASY (E01–E40) | 2:00 | **12 points** | 0 |
| BONUS | at 12 → one easy | 1:00 | **+3 = perfect 15** | stays 12 |
| BONUS | at 0 → one easy | 1:00 | **10 points** | stays 0 |

The bonus round runs only if time remains after everyone's main turn. Students who
solved a HARD are already at the perfect 15.

## Flow

1. Student clicks **EASY** or **HARD** → a random *unused* problem loads **instantly**
   into the editor (numbers never repeat; counters in the header, `reset draws` to clear).
2. The editor has line numbers and real **NetBeans-light syntax coloring** — keywords,
   strings, comments, numbers — but **no error marking** (that's the point), with
   `package debugduel;` already on top and the GOAL as a comment.
3. Student fixes the code right there. Timer below (editable minutes, presets
   3:00 / 2:00 / 1:00 bonus, beeps at zero).
4. **⧉ Copy all** → paste into NetBeans `Main.java` (Ctrl+A, Ctrl+V) → **Run**.
   The Output window is the judge: goal printed within the time = points.

## Completed problems

Every loaded problem is automatically marked **completed** — it can never be drawn
again for another student. The **Completed Problems** section at the bottom shows all
used numbers as chips in order (E01 … E40, H01 … H20); click the **×** on a chip to
restore that problem to the pool (handy for the bonus round or a cancelled turn).
`reset draws` in the header restores everything.

State is saved in the browser's local storage, so a page refresh during the activity
keeps your completed list — when running from a normal origin (the downloaded file
opened locally, or GitHub Pages).

## Problem sets

All 60 problems (40 easy · 20 hard) are embedded — every fixed version has been
compiled and run against a real JDK. To load a different set later, click
**⇪ import** and paste a whole master file; the app reads every numbered block
automatically.

---

Built for the ACT 102 *Java Basics and Fundamentals* module.
