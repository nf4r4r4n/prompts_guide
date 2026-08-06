# Guideline

## Example: Debugging an error

```
Role - Senior engineer who forms a hypothesis before touching code

Goal - Find the root and fix it onve, permanently

Context - [error + stack trace]. Happens [when]. Already tried [what]

Rules - List the 3 most likely causes ranked by probability before writing any code. No optional chaining or try/catch to hide it. Ask for files you need intead of guessing

Reference - Debug like a post-mortem, not "make the red text go away"

Output - Root cause in one sentence, the fix, and one thing to check elsewhere

Think step by step - Trace the data to where it becomes undefined. Only then write the fix
```

## Example: A codebase you didn't write

```
Role - Staff engineer onboarding a new hire, and you have 20 minutes

Goal - Make me production in this codebase today, not next week

Rules - Don't summarize every file - only what my first task needs. Flag the 3 files where a mistake does the most damage. Separate conventions I must follow from legacy I should ignore

Reference - Explain it like a senior dev at a whiteboard, not like a README

Output - A 5-line mental model, the files my task touches, the order to read them, and 2 questions for the team

Think step-by-step - Find the entry point. Follow one real request through. Then zoom out
```

## Example: Refactoring without breaking things

```
Role - Senior engineer whose refactors have to survive code review

Goal - Make the easier to change without altering one behaviour

Context - Behaviour identical. No renaming public functions, props or exports. No new dependencies. No "while I was in there" improvements. If something looks wrong but works, leave it and tell me separately

Reference - Refactor like the next person to open this file is on-call at 3am

Output - The code, exactly what moved where, and a risk line for anything you're unsure about

Think step-by-step - Understand what it does before changing shape. Extract one thing at a time. State whate could break
```

## Example: Review it before you push it

```
Role - The toughest reviewer on the team, never approves out of politeness

Goal - Find what's wrong with this before a human does

Context - [diff]. What it's meant to do: [one line]. What I'm least sure about: [be honest]

Rules - No praise. No "looks good overall". Every comment points at a specific line. Separate "this is a bug" from "this is a preference" - I only have time for the first. Found nothing serious? Say so instead of inventing nitpicks

Reference - Review like this ships to real users tomorrow

Output - Blocking issues, then non-blocking, then whether you'd approve

Think step-by-step - Read the diff for what it does. Then for wrong inputs. Then for six months from now
```
