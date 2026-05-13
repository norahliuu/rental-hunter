---
name: rental-hunter (留住)
description: Research and analyze student rental apartments using listing websites, Reddit, Xiaohongshu, floor plans, commute analysis, and resident reviews.
---

> **Language/语言**： This skill support both English and Chinese. 
> 本skill支持中文与英文
---
# Rental Hunter
## Purpose
This skill helps students find suitable apartments or rental housing near their school.

The assistant should:
- search rental listings
- estimate walking time to campus/main class buildings
- analyze building quality
- collect community reviews
- locate floor plans
- summarize pros and cons
- generate a structured report

This skill is optimized for international students.

---

## When to use skill
Describe activation conditions.

Use this skill when the user:
- wants to search for apartments
- compares condos/buildings
- asks about commute/living experience
- requests rental reports

Do NOT use this skill for:
- legal lease review
- roommate conflict advice
- mortgage/home purchase analysis
---

## Required Inputs

### Required
- city
- school
- budget
- room_type
- max_walking_time_to_school

### Optional
- move_in_date
- preferred_features
- furnished
- pet_friendly


If invoked as `/rental-hunter $ARGUMENTS`, parse the arguments as:
```
/rental-hunter [city] [school] [budget] [beds]
# Examples:
/rental-hunter Toronto "U of T" 1800 1bed
/rental-hunter Vancouver UBC 2000 2bed
/rental-hunter Waterloo "Wilfrid Laurier" 1400 studio
```
---
## Missing information handling
If required arguments are missing:
- ask concise follow-up questions
- gather enough information before searching

If optional arguments are missing:
- continue using broader search criteria
- do not repeatedly ask the user
- mention assumptions clearly in the final report

If the user says:
- "not sure"
- "anything is okay"
- "skip this"
- "no preference"

then treat the argument as unspecified and continue.

---

## Default Assumptions

If move_in_date is unspecified:
- prioritize currently available listings

If room_type is unspecified:
- include studios and 1-bedroom units

If language_preference is unspecified:
- respond in the same language as the user

---

## Language Handling

If the user's input is Chinese:
- prioritize rednote(xiaohongshu) and Chinese-language sources
- respond in Chinese unless otherwise requested

If the user's input is English:
- prioritize Reddit and English-language sources
- respond in English unless otherwise requested

---
## Workflow

### Step 1 — Collect User Requirements

Gather:
- city
- school
- budget
- maximum walking time to school
- optional preferences

Clarify missing required arguments before continuing.

---

### Step 2 — Search Rental Listings

Search local housing listing platforms such as:
- condos.ca
- rentals.ca
- realtor.ca
- student housing websites

Collect:
- address
- monthly rent
- bedrooms/bathrooms
- square footage
- amenities
- availability
- listing images

---

### Step 3 — Estimate Walking Time

Estimate realistic walking time from the property to the user's school.

Use realistic pedestrian routes instead of straight-line distance.

Prioritize listings within the user's walking limit.

Listings slightly outside the limit may still be included if they provide exceptional value.

---

### Step 4 — Research Building Reputation

Search:
- Reddit
- Xiaohongshu (Rednote)
- Google Reviews
- student forums

Summarize:
- safety
- noise
- management quality
- cleanliness
- elevator reliability
- internet quality
- package and uber deliverytheft
- student friendliness
- hidden problems

Prioritize recent reviews whenever possible.

---

### Step 5 — Find Floor Plans

Search for:
- official floor plans
- archived listing images
- developer brochures
- previous rental listings

If no floor plan is found:
- clearly state that no floor plan was available

Do not hallucinate floor plans.

---

### Step 6 — Rank Listings

Prioritize:
1. walking distance to school
2. price
3. resident reviews
4. floor plan quality
5. building amenities

Avoid ranking based only on luxury amenities.

Student practicality should be prioritized.

---

### Step 7 — Generate Final Report

Generate a structured report for each recommended property.

Include:
- building name
- address
- price
- walking time
- nearby transit
- nearby grocery stores
- floor plan image 
- resident opinions
- pros and cons
- overall recommendation

Use tables and bullet points whenever possible.

The general layout of the report should be:

Title: [school_name] rental hunting
Date generated: [current date]

Give the top 10 ranking buildings that suits the user's preferrence 
Divide the mainbody of the report into sections, where each section introduces one building. 

---

## Output Style

The report should be:
- concise
- structured
- research-oriented
- student-focused

Prefer:
- bullet points
- tables
- short paragraphs

Avoid:
- excessive marketing language
- vague recommendations
- unsupported claims

Clearly mention uncertainty when information is incomplete.

---

## Example User Requests

- "$rental-hunter find studios near UofT under 2400"
- "$rental-hunter compare CampusOne and Parkside"
- "$rental-hunter apartments within 15 minutes walking to Waterloo"

---

## Failure Handling

If insufficient listings are found:
- relax optional filters first
- keep required filters unchanged

If information is unavailable:
- clearly state limitations
- avoid fabricating missing details

If listings appear outdated:
- prioritize newer sources
- warn the user about uncertainty

