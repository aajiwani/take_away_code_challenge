# Takeaway.com Code Challenge

## Running the solution

All the steps to run the solution is documented [here](./running_steps.md). Please go through them in order to run the solution successfully.

---

## Problem Statement

To streamline all transactional emails within Takeaway we want a transactional email
microservice. This service should make sure transactional emails are sent with a high degree of
certainty.

---

## Expectations

This microservice will use external services to actually send the emails.
When such an external service is unavailable there should be a fallback to a secondary service.
In the future, there probably will be more fallbacks so this should be taken into account.

At first, this microservice should be able to send an email by an (JSON) API and through a CLI
command. We also want to have a log entry for every email that is sent through this
microservice.

To improve the speed of the API calls the sending should happen asynchronously (use the
queuing technique of your own preference).

---

## Requirements

Make sure;
- The micro-service is horizontally scalable
- The code has tests
- You’re including a readme which describes the choices you made and why
- You’re using micro-commits
Important: ​ we'll only have Docker running on our machines and should not have to install any
additional software to get this micro-service running.

### Bonus points
- Allow multiple mail formats
- HTML
- Markdown
- Text
- Allow more recipients
- Create a simplified separate “consumer self-service” (micro)service with endpoints for
registration and forgotten password
- Sending the following emails
- (New) customer registered
- Password forgotten○ Make it handle potential downtime of mailer-service gracefully

### Out of scope
Don't worry about the authentication/authorization for this microservice for now.

### Required techniques:
- Docker
- PHP
- MySQL (or any other data storage)

### Preferred techniques:
- Laravel/Lumen/Symfony