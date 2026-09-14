# Nexus

Nexus is a networking platform and CS aptitude benchmark designed to test how strongly you apply
critical CS skills to realistic situations. This benchmark tests basic prerequisite knowledge as well
as how you apply it to realistic problems.

The platform combines standardized testing, percentile-based scoring,
public profiles, leaderboards, and social features into a single system.

**Live Site:** [https://chance581.github.io/nexus-prototype/]
**Portfolio:** [https://chance581.github.io/chanceportfolio/]

## Overview
Nexus was designed because traditional markers of computer science aptitude, such as GPA and self-reported skills
are insufficient for measuring raw skill.

While sites for improving at programming such as LeetCode exist, they are tailored towards interviews and specific
implementation. The goal of Nexus is to test knowledge of basic CS principles and how well you can apply them to
realistic problems.

Nexus will assign you a score and composite percentile to know how you are performing relative to your peers. You
also get score-specific breakdowns to determine what you can improve on.

The platform also has networking functionality, allowing you to connect to others who are interested in CS, whether
for mentorship or to find peers at a similar level of knowledge.

## Features

### Benchmarking
- Multiple computer science assessment categories
- Section-level scoring
- Composite performance scoring
- Percentile-based results
- Public performance profiles
- Leaderboards
- Confidence indicators based on testing history

### Platform
- User authentication and profiles
- Discussion forums
- Direct messaging
- Notifications
- Public user profiles

## Technical Architecture

Nexus uses a client-server architecture centered around a Supabase backend.

### Frontend

The frontend is implemented with HTML, CSS, and JavaScript. Client-side
state is used to manage authentication, test sessions, profiles,
leaderboards, forums, and messaging.

### Backend

Supabase provides authentication, PostgreSQL database functionality,
row-level security, database functions, and backend data management.

### Database

The PostgreSQL database stores users, questions, test attempts, scores,
profiles, forum content, messages, and notifications.

Database functions are used for critical operations that require server-side verification
including test grading and score calculation.

### Security

Row-Level Security policies restrict access to protected data at the
database level rather than relying exclusively on frontend checks.

Private question data is separated from publicly accessible question
information so that correct answers cannot simply be retrieved by the
client.

### Scoring

Test results are processed into section scores and composite performance
metrics. Percentiles are calculated relative to the relevant benchmark
population rather than being treated as raw scores alone.

## Technical Highlights

### Database-Level Authorization

Because Nexus contains private user information, test questions, and
user-generated content, authorization cannot safely depend on frontend
logic alone.

Nexus uses PostgreSQL Row-Level Security policies. This allows the database to independently
restrict which records users can read or modify. For example users much rely on a server-side function
for grade submissions rather than being able to modify their own scores.

This approach reduces the risk of exposing personal information and reduces the likelihood of
users being able to cheat on the aptitude test.

## Development

Nexus was developed indepdently from its initial
prototype through deployment.

Development focused on progressively expanding the system while keeping
the core benchmark functionality reliable. Some major design decisions include the following.

Moving grading from the frontend to the backend to prevent false score submissions.

Adding compatibility for additional tests to further differentiate users.

Created a confidence interval function to prevent small samples of tests from giving users unreliably high/low scores.

## Project Status

Nexus is currently functional and deployed.

Implemented:
- [x] Authentication
- [x] Computer science assessments
- [x] Automated scoring
- [x] Percentile calculations
- [x] User profiles
- [x] Leaderboards
- [x] Forums
- [x] Direct messaging
- [x] Notifications

Planned:
- [ ] Expanded assessments to other fields
- [ ] Finalize advanced benchmark
- [ ] Improved moderation tools
- [ ] Additional analytics
- [ ] Expanded networking functionality

## Running Locally
Not available currently. I plan to release a modified version of my Supabase code which includes
relevant functions, tables, and RLS policies without exposing sensetive information about user data or questions.

## Why I Built It
I noticed that there were limited resources for CS Students to network, and no generalized CS aptitude tests.
I built Nexus to allow students to get a general idea of their current aptitude and be able to network with
others based on demonstrated results.

## Future Development
Potential improvements/features.

## Author
Created by Chance. CS student at the University of Michigan.
