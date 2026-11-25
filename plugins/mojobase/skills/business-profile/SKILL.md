---
name: business-profile
description: Fill in or update the business profile in Mojobase's Handbook (what the business sells, prices, customers, tone of voice, policies, people) from what the person has told Claude or shared in this conversation. Every agent and every one of Mojobase's own runs reads it first. Use when someone sets up Mojobase, says "tell Mojobase about my business", or asks to update the business profile, prices, tone or policies there.
---

# Business profile

Needs Mojobase connected. Pass `author: "claude"`, `model` (your model id) and a one-sentence `reason` on the
change.

The business profile is the brief that every agent and every scheduled run in Mojobase reads before it writes
anything for the business. Claude often knows the business better than an empty form does: this skill moves what it
knows into Mojobase, and invents nothing.

## Steps

1. **Read what's there.** `knowledge_business_profile`. It gives the profile's text, its `version`, its `status`
   (Approved, Draft, or Changed by AI since approval) and `fill_ins_left`. If it isn't set up, it gives the template
   to start from.
2. **Gather what you already know.** What the person has told you or shared in this conversation. Only facts
   you actually have: prices exactly as written, people's names and roles as
   given, policies in their own words.
3. **Ask only for what matters most.** If what's missing is something every reply depends on (what they sell, their
   prices, their tone), ask the person for up to three of those. Everything else stays a fill-in.
4. **Write it.** Start from the template or the current text and keep its headings. Replace a `{{fill-in}}` only
   with a fact you have; leave the rest exactly as `{{fill-ins}}`. When updating, change only what the person asked
   or what you now know better, and keep the rest word for word.
5. **Save it.** `knowledge_business_profile_update` with `body` (the whole profile in Markdown), `reason`, and
   `version` from step 1 when a profile exists. If the version changed since, nothing is saved: read it again and
   redo step 4.
6. **Tell the person.** It's saved as a Draft under your name for them to check in Mojobase's Handbook, an
   approved profile goes back to Draft until they approve it again, and list the fill-ins still left.
