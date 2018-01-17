# Mindflash Backend Coding Exercise
Our goal is to give you a small coding challenge that allows you to demonstrate your skills and also gives you a small idea of some of problems that you may encounter at Mindflash. We know you're busy with life, so our aim is to have you spend no more than 2 hours working through this exercise. We don't expect you to finish in 2 hours, so don't worry if you can't. Submit what you have along with some notes on your thoughts and how you would proceed if you have more time. Most importantly, try to have some fun with it!

## Task
Your task is to build a small dockerized application that filters, transforms, and indexes a stream of events into Elasticsearch (ES). To help you get started, we've included a [docker compose](https://docs.docker.com/compose/overview/) file to set up your local environment.

## Overview
You just got hired to join the *badass* engineering team at *BrainSpark*, the world's leading LMS! The first story in the sprint assigned assigned to you is to build an application that indexes a stream of events into ElasticSearch for use in reporting and general anaytics. For reference, the domain model of our application for the exercise is shown below:

<p align="center">
<img src="./schema.png" align="center" alt="schema diagram" />
</p>

At a high level:
- Our product supports multiple accounts
- Each account has many courses and many users
- A user may attempt a course many times
- Users can perform actions that trigger events

Our focus for this exercise are the domain events. Events are published via an [NSQ Topic](http://nsq.io). The event topic messages represent a single domain event and are serialized as JSON. A sample event is shown below: 

**Sample NSQ Event Message:**
```json
{
    "id": "5c92de28-14f0-449e-821b-e61e871179c2",
    "attempt_id": "e70a6ecf-f308-4306-831d-bb41c851061d",
    "progress": 0.63414633,
    "score": 0.96158886,
    "timestamp": "2018-01-16T14:09:51.655185082-07:00",
    "type": "PROGRESS",
    "user_id": "471de972-520c-4f44-bd6d-34cc98dd5e6e"
}
```

Prior to indexing the event records into ES, you will need to apply the following transformations:
- filter out invalid messages (ie messages that do not pass the schema above)
- filter out events with type `FOO`
- denormalize the event by *hydrating* (ie *embedding*) the related attempt, course, trainee, and user (if available) using the *BrainSpark* API (see details section below for more info)

An example of a successful transformation is shown below:

**Sample Transformed ES Document:**
```json
{
    "id": "5c92de28-14f0-449e-821b-e61e871179c2",
    "timestamp": "2018-01-16T14:09:51.655185082-07:00",
    "type": "PROGRESS",
    "attempt_id": "e70a6ecf-f308-4306-831d-bb41c851061d",
    "progress": 0.63414633,
    "score": 0.96158886,
    "user_id": "471de972-520c-4f44-bd6d-34cc98dd5e6e",
    "attempt": {
        "id": "e70a6ecf-f308-4306-831d-bb41c851061d",
        "course_id": "9a3c3136-c24d-4fb6-94fe-7ba6aa491080",
        "created_at": "2017-07-09T00:45:24.466Z",
        "trainee_id": "747f457c-7e74-400e-9b0e-071d1c693ea4",
    },
    "course_id": "9a3c3136-c24d-4fb6-94fe-7ba6aa491080",
    "course": {
        "id": "9a3c3136-c24d-4fb6-94fe-7ba6aa491080",
        "account_id": "aacf3f09-4b19-424f-995a-4b13f8e36365",
        "name": "hot dog vs not hot dog"
    },
    "trainee_id": "747f457c-7e74-400e-9b0e-071d1c693ea4",
    "trainee": {
        "id": "747f457c-7e74-400e-9b0e-071d1c693ea4",
        "account_id": "aacf3f09-4b19-424f-995a-4b13f8e36365",
        "first_name": "erlich",
        "last_name": "bachman",
        "email": "e.bachman@bachmanity.com"
    },
    "user": {
        "id": "471de972-520c-4f44-bd6d-34cc98dd5e6e",
        "account_id": "aacf3f09-4b19-424f-995a-4b13f8e36365",
        "first_name": "jin",
        "last_name": "yang",
        "email": "jin.yang@seefood.com"
    }
}
```

The events need to be indexed into the `trainee-events` index, with type `trainee-event`.

Details:

Requirements:

Expectations:

Submission: