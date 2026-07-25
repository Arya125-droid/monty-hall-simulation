# 🚗 The Monty Hall Problem — Complete Analysis & Simulation

> *"The puzzle that made 10,000 people write angry letters to the world's smartest woman. She was right. They were wrong. This repository proves it."*

---

## Table of Contents

- [What Is This?](#what-is-this)
- [The Problem](#the-problem)
- [The Answer](#the-answer)
- [Why Your Intuition Is Wrong](#why-your-intuition-is-wrong)
- [The Math](#the-math)

---

## What Is This?

This repository is a **complete, ground-up exploration** of the Monty Hall Problem —
one of the most famous and most argued-about puzzles in probability theory.

It covers everything:

**Intuition** Plain English explanations anyone can follow |
**Math** Full Bayes' Theorem proof built from scratch |
**Code** Python simulation across 100,000 trials |
**Visuals** Convergence plots, probability shift charts |
**Interactive** Play the game yourself in the terminal |

---

## The Problem

In 1963, a game show called *Let's Make a Deal* aired a puzzle
that would confuse the world for decades.

There are 3 closed doors.
Behind ONE door -> Brand new Car
Behind TWO doors -> Goat


**Step 1** — You pick a door. Say, Door 1.

**Step 2** — The host (Monty Hall), who *knows* where the car is,
opens one of the other doors — always revealing a goat.

**Step 3** — Monty asks: *"Do you want to STAY with your door, or SWITCH to the other closed door?"*


### What do you do?

## The Answer
ALWAYS SWITCH
Switch -> wins 66.7% of the time 
Stay -> wins 33.3% of the time 


In 1990, **Marilyn vos Savant** published this answer in Parade Magazine.
She received over **10,000 letters** — most calling her wrong, many from credentialed mathematicians.

She was correct. Every single time.

This repository shows exactly why — three different ways.

---

## Why Your Intuition Is Wrong

Your brain sees two closed doors and says *"50/50."*

Here is why that is wrong:
When you first picked Door 1:

You were RIGHT -> probability = 1/3 (33%)
You were WRONG -> probability = 2/3 (67%)

Monty opening a door does NOT change what
your original pick was worth.

Your door stays at -> 1/3
Monty's open door -> 0 (confirmed goat)
The switch door -> 2/3 <- all remaining probability collapses here

---


### The 100-Door Version

Still not convinced? Scale it up:

100 doors. 1 car. 99 goats.

You pick Door 1. → 1% chance you are right.
Monty opens 98 doors. → All goats.
One door remains: Door 57.

Monty had 99 doors to open.
He opened 98 of them.
He specifically left Door 57 closed.

**Why?**

Because 99% of the time — the car is there.

STAY → 1% chance of winning
SWITCH → 99% chance of winning


Same logic. Three doors. Always switch.

---

## The Math

### Basic Probability

P(car behind Door 1) = 1/3
P(car behind Door 2) = 1/3
P(car behind Door 3) = 1/3

After Monty opens Door 2:

P(car behind Door 2) = 0 ← confirmed goat
P(car behind Door 1) = 1/3 ← unchanged
P(car behind Door 3) = 2/3 ← absorbs the collapsed probability


### Bayes' Theorem

For those who want the full formal proof:
P(A|B) =      P(B|A) × P(A)/P(B)

Where:
A = car location hypothesis
B = Monty opens Door 2

P(Monty opens D2 | Car=Door1) = 1/2 (he can open D2 or D3)
P(Monty opens D2 | Car=Door2) = 0 (he never opens the car door)
P(Monty opens D2 | Car=Door3) = 1 (he must open D2)

P(Monty opens Door2)
= (1/2)(1/3) + (0)(1/3) + (1)(1/3)
= 1/6 + 0 + 2/6
= 1/2

P(Car=Door1 | Monty opens D2) = (1/2 × 1/3) / (1/2) = 1/3 ← STAY
P(Car=Door3 | Monty opens D2) = (1 × 1/3) / (1/2) = 2/3 ← SWITCH


---

*Built with Python · Proved with Bayes · Settled forever*

