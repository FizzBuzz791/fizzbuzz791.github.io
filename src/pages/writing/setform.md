---
layout: "../../layouts/WritingLayout.astro"
title: "Setform: Structured Swim Training Meets AI-Assisted Development"
description: "Capturing the intent behind swim workouts while exploring how ChatGPT and GitHub Copilot can accelerate modern software development."
pubDate: 2026-07-13
---

## What is Setform?

[Setform](https://setform-app.netlify.app/) started with a simple frustration: despite the number of fitness platforms available today, none of them captured a swim workout the way I actually thought about it.

Garmin records GPS data, heart rate, and lap times. Strava is excellent for analysing completed activities. TrainingPeaks excels at planning. But none of them let me accurately record the structure of a squad training session while preserving the rich telemetry my watch captured.

Setform is an experiment in combining those two worlds.

The goal is not to replace Garmin or Strava. Instead, it acts as the missing layer between planning, recording and analysing structured swim workouts.
The Problem
Competitive swim sessions are highly structured.

A typical session might consist of:

- warm-up
- drill sets
- kick sets
- threshold work
- sprint efforts
- recovery swimming
- cool down

Each set has its own distance, target pace, interval and coaching notes.

Most fitness platforms flatten this into little more than a timeline of laps. While the raw telemetry is valuable, it loses the intent behind the workout.

For example, there is no obvious way to answer questions like:

- How often am I swimming threshold work?
- Which drills improve my stroke efficiency?
- Am I consistently missing target intervals on longer aerobic sets?
- Which sessions produce the biggest improvement in SWOLF?

The data exists, but not in a form that's easy to analyse.

## The Approach

Setform treats workout structure as the primary data, focusing on capturing the intent behind each session to meet the needs of dedicated swimmers and developers.

Each workout stores a structured representation of every set, including:

- distance
- repetitions
- interval
- stroke
- equipment
- notes

External platforms then become sources of telemetry rather than the canonical record of workouts.
Garmin, Strava and FIT files provide metrics such as:

- heart rate
- pace
- SWOLF
- elapsed time

## Technical Design

Setform is built using:

- React
- TypeScript
- Supabase
- Netlify
- GitHub Actions

Supabase handles authentication and persistence, while deployments are fully automated through GitHub Actions.

One interesting design decision was to avoid over-normalising the workout model deliberately.

Rather than modelling every possible set variation as dozens of related database tables, the workout itself is stored as structured JSON. This structure provides enough flexibility to represent almost any session while keeping the relational model relatively simple.

As the product matures, the challenge becomes extracting meaningful analytics from that flexible structure without sacrificing query performance.

## Building with AI

Setform also became an experiment in modern software development workflows.

Rather than treating ChatGPT as a code generator, I used it primarily as a planning tool. Features were discussed and refined through conversation before being broken down into GitHub Issues that GitHub Copilot could implement independently.

This separation of responsibilities turned out to be surprisingly effective.
ChatGPT excelled at:

- exploring requirements
- identifying edge cases
- proposing architecture
- breaking larger ideas into manageable units of work

GitHub Copilot then became the implementation engine, taking well-defined issues and producing complete pull requests for review.

The workflow was considerably more productive than asking either tool to perform the entire task alone.

## What Didn't Work

The biggest gaps appeared around integration rather than implementation.

Infrastructure setup still required significant manual intervention. Configuring Supabase, creating OAuth applications, managing secrets, copying callback URLs and wiring together external services often required dropping back into ChatGPT for guidance.

These weren't failures of the tooling so much as gaps in the instructions I provided. Looking back, many of these interruptions could probably have been avoided with more comprehensive project prompts and explicit setup documentation.

That has become one of the key lessons from the project: the quality of the planning directly affects how autonomous the implementation can be.

## Looking Ahead

Setform continues to evolve as both a swim training platform and an experiment in AI-assisted software development. While there are still features I'd like to build, the project has already achieved one of its original goals: demonstrating that a combination of thoughtful planning, well-defined issues and AI-assisted implementation can produce maintainable software with surprisingly little manual coding.
