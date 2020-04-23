# HW4-DevOps

### Building Monitoring Infrastructure

* Tasks 1--5 completed, please check the screencast below.

### Screencast

[Click here to view the screencast](https://drive.google.com/open?id=171mad6avsXsuluGrb3B5eXnN7O2dRRpb)

### Conceptual Questions

1. Compare a channel deployment model with a ring deployment model.
- **Channels deployment model** changes test in channel. After 2 weeks, changes promoted to next channel, unless fast tracked or booted by release engineer. This is a good model for easily rollback and for those with high delivering costs. Although **Ring model** shares a lot of similarities with the channel model, ring model changes who actually get it. It promotes change from internal users to early adopters and wider and wider group of users. Change can stay in ring for weeks.


2. Identify 2 situations where an expand/contract deployment could be useful.
- Parallel Change: try to make a change in the server, however some updates can block read/write operations. It's the case you want to deploy co-changes to two dependent but seperate systems without downtime. The expand enables adding a new field and do a duplicate write, then migrate them in the database. The contract step removes the reference and drop it. It's a good way to coordinate in co-systems such that there are no blocking operations.

- Database Refactoring: Most database refactorings follow the expand/contract pattern, where the migrate phase is the transition period between the original and the new schema, until all database access code has been updated to work with the new schema.


3. What are some tradeoffs associated with dark launches?
- **Benefits:**
  - **No release branches**. Can help eliminate the need to support long-running release branch. Reduces merge issues.
  - **Allows stability and experimentation**. Developer can test in production--for example, test load speeds for recent images without user needing to see. Can conditionally turn on for some segments of users to gather usage data.
  - **Improve disaster recovery**. No rollback, just turn off feature.

- **Issues:**
  - **Technical debt**. Removing flags is a highly variable practice. Reusing old flags can be disastrous.
  - **Mixed experiences**. Inconsistent user experiences can reduce satisfaction.
  - **Stability**. Supporting multiple permutations of software can increase engineering costs and reduce stability.


4. Describe the Netflix style green-blue deployment. What can canary analysis tell us?

- **Netflix style:** The deployment a new version of an app will start to receive traffic as soon as it passes health checks. Once the green version is healthy, the previous blue version is disabled and receives no traffic. If a rollback is needed, making a change is as simple as enabling the previous version. This model allows to move fast and get back to a known good state if something goes wrong.

- **Canary analysis:** can characteize system behaviors as "Pass", "High", "Low", by comparing between canary and baseline metrics. Also, it enables checking if meeting capacity requirements by gradually ramping up load.
