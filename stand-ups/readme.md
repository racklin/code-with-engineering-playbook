# Stand-ups

The stand-up is a ceremony that is held each day of the sprint. In this ceremony, each contributor will answer three simple questions. This will repeat until each contributor has answered the three following questions.

1. What did you work on yesterday?
2. What are you working on today?
3. Do you have any impediments/blockers? (defer discussion / resolution to "the parking lot", described below)

After that point, the stand-up is concluded. There may be a parking lot discussion after. However, participation in the parking lot discussion is optional for all members except those explicitly needed for discussion of the issues raised.

The term parking lot refers to a bucket of comments, concerns, or questions that will be discussed and/or addressed at a later point with potentially fewer contributors. This is part of a strategy to avoid letting the discussion in a meeting shift to a subject that is not aligned with the meeting goals and/or decisions.

## Goals

1. Bring awareness to the contribution of each member for the past and upcoming day.
2. Surface any impediments to one or more team members' contributions.

## Participation

The entire team should attend the stand-up. Anyone that worked on a task towards the sprint work should answer the three questions. It would be up to the team to decide if they would like updates from members that are not directly working against sprint task work (i.e. Product Owners and Program Managers).

- Scrum Master (Required)
- Product Owner (Optional)
- Program Manager (Required)
- Dev Manager (Required)
- Tech Lead + Contributors (Required)

## Impact

Team members get a clear understanding of what development tasks are going on within the team which helps with collaboration. It also provides a time to address any challenges or blockers that may be stopping specific tasks from being completed, therefore helping with velocity.

## Measures

Both stand-up length and time to start are important as the stand-up has to be seen as a reliable and efficient meeting that facilitates communication of information versus unnecessary overhead.

### Stand-up Length

While the length can depend on the team size, if everyone is sticking to one line answers to the 3 key questions, it should be fairly easy to conclude within 5-10mins.

#### Example (team size == ~8)

- 1-5 min = Excellent
- 5-10 min = Great
- 10-15 min = Good
- 15+ min = Needs Improvement

### Time to Start

How long after the scheduled start time did contributors begin providing updates?

- 0-1 min = Excellent
- 1-3 min = Great
- 3-5 min = Good
- 5+ min = Needs Improvement

### New Tasks Created After Stand-up

How many tasks are being generated after the stand-up that didn't exist before? This can indicate how much unplanned work is being done. If creating new tasks after stand-up becomes routine (especially for the same story), this could indicate the story is at higher risk of not being completed. It could also indicate a shift in focus to an unplanned objective.

## Facilitation Guidance

The scrum master should facilitate the stand-up meeting.

### Speak to Tasks

When answering what was worked on and what will be worked on, refer directly to tasks. This has two benefits:

1. The answer will naturally be short (e.g. "I finished task 114 yesterday; which was to update the build of the api container image. I will be starting on task 115 today; which is to update the release pipeline for the same container image.").
2. Unplanned work will be easily identifiable. If the person is unable to refer to a task, that typically indicates they are working on something unplanned or out of scope for the sprint (e.g. Yesterday, I was attempting to optimize some of the unit tests from last sprint to run faster).

If a contributor is not working on an existing sprint task they need to either create a new task under an existing sprint story to reflect that work, or defer that work until its scheduled for a later sprint.

**If a contributor provides an update without referring to a task, ask the contributor which task.**

### Parking Lot Discussion Items

As contributors are answering the three questions, if another contributor has a question or issue to share, they should reserve until after all contributors have answered finished. Once each member has answered all three questions, the scrum master should open up the floor to anyone who may have an open question or unresolved issue to share. This portion of the ceremony is often referred to as the "Parking Lot".

**Parking lot discussions are optional for participants**. Ensure discussion leaders call out necessary parties for their discussion points upfront, allowing those not needed to leave the meeting.

### Start On Time

Make a best effort to begin answering the 3 questions as close to the scheduled start time as possible. Try not to waste time upfront on chit-chat or waiting on all team members to join. This can extend the meeting time significantly. Starting immediately will help ensure stand-ups remain effective and useful over time.

### Same Time Everyday

Stand-up should be held at the same time each day. The meeting time should be mutually agreed-upon by the contributors, and should take into consideration time zones, working schedules, and other factors so that every team member can reasonably participate.

### Schedule Stand-ups for Mid-Morning

```
             ((((
            ((((
             ))))
          _ .---.
         ( |`---'|
          \|     |
          : .___, :
           `-----'
```

Many teams find that the ideal time for stand-ups is between 9 and 10am. This provides ample time for team members to get into the office, settle in (`grab a coffee ;)`), and catch up with where they left off the day before. It's also early enough to help developers to plan their day around new work items.

For teams distributed across time zones, consider scheduling standup between 9 and 10am within the time zone that has the most team members.

### Contributors Unable to Attend (async updates)

If a contributor knows that they will have to miss the stand-up, ask them to provide their answers to the 3 questions in written form before the stand-up. They could provide these over a shared Teams channel or email to the team. The scrum master can then read the answers during the stand-up. Reading the update aloud during the stand-up will ensure the answers are communicated to the team.
