# nsp
 POC to show how to use docker containers and azure devops with Azure to deploy microservices/frontends

/build - dev builds
/deploy - deployment pipelines
/src - code goes here
readme.md - Documentation and entry points

# In Practice
Each BU expose apis to establish contracts so that business rules are encapsulated and maintained independent of infrastructure and other BUs (bounded context).

All APIs secured. In this case, we use a jwt to secure api endpoints.

# Random thoughts    
* Gotchas: dependency on file system, operating system, db triggers, direct    dependencies on tables outside of bounded context.
* Need a collaborative and well-known architectual vision. Need small goals to get from where we now to where we want to be. Still keep individual teams' autonomy while creating a pattern for best practices.
* Need to improve knowledge sharing - instead of funneling knowledge through SDs, make it a collaborative process where everyone owns and maintains it. 
* New policies/procedures/direction on where the company is headed from an IT perspective could be better communicated to department.
* Retries, rate limits
* Challenges: source of truth with shared data (i.e. company info, benefits packages, pay frequency etc)
