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

1. Student clicks **EASY** or **HARD** → a roulette draws a random *unused* problem
   (numbers never repeat; counters in the header, `reset draws` to clear).
2. The problem loads into the editor — line numbers, light NetBeans-style theme,
   **no error hints** (that's the point), with `package debugduel;` already on top
   and the GOAL as a comment.
3. Student fixes the code right there. Timer below (editable minutes, presets
   3:00 / 2:00 / 1:00 bonus, beeps at zero).
4. **⧉ Copy all** → paste into NetBeans `Main.java` (Ctrl+A, Ctrl+V) → **Run**.
   The Output window is the judge: goal printed within the time = points.

## Problem sets

All 60 problems (40 easy · 20 hard) are embedded — every fixed version has been
compiled and run against a real JDK. To load a different set later, click
**⇪ import** and paste a whole master file; the app reads every numbered block
automatically.

---

Built for the ACT 102 *Java Basics and Fundamentals* module.
