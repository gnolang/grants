## Project Name
Shiken

## GitHub handle
@gfant (previously @iam-agf)

## Email

genericaldeveloper@gmail.com

## Links (Twitter, website, etc.)
[Linkedin](https://www.linkedin.com/in/gfantoni71/)
[Twitter](https://x.com/jkstoc)
Discord - gfant

## Project summary

This is a renew of [the previous application of this Grant Request](https://github.com/gfant/ecosystem-fund-grants/blob/main/shiken.md).

The original goal of the Shiken project was to tackle the [issues around hiring people with certain confidence about the candidate' skills](https://github.com/gnolang/hackerspace/issues/13)
Currently this idea has changed and can be summarized into: giving the GNO ecosystem a platform where the developers community can test their skills based on problems stablished by a DAO.
### Goals and deliverables

## Goals and deliverables

The Shiken Project composes of three parts that are already under construction

The deliverables for this project composes in four parts:

* The realm that will store the data and manage the leaderboards. [(link)](https://github.com/gfant/shiken-realm)
* A website to facilitate tackling the problem. [(link)](https://github.com/gfant/shiken-web)
* An API that will handle the connection between the website and the realm. [(link)](https://github.com/gfant/shiken-api)
* A Dockerfile to be able to run all the pieces in a server. [(already in package `shiken-api`)](https://github.com/gfant/shiken-api)

Worths to be mentioned that there are several parts with a huge progress.

Each bullet is a deliverable by itself. In order, the path of deliverables would be

1. The Realm
2. The API
3. The Website
4. The Dockerfile

In that order, since the next deliverable highly depends on the previous ones.

## Impact on gno.land’s developer ecosystem

The original idea for this project was to attend [the need of a better hiring process](https://github.com/gnolang/hackerspace/issues/13).
As result of several conversations with members of the GNO team, this project can also facilitate to determine the historic of a candidate to see if has the required skills for a position or to receive a grant and be adapted as a tool for teaching new developers how to learn about GNO or have a record of their learning path.

## Timeline and milestones

Currently the project is more than half its progress:

#### What is done

- A proof of concept of the website. Is functional for the purpose to execute and test the completed parts of the Realm.
- Realm with
    - Data storing of the Problems
    - Data storing of the Leaderboards for the problems.
    - Certain parts involving the update of the user data based on the attempts/solutions of the users
- API already functional to handle receiving the code of the users and based on the result send the information to the realm.
- An AWS environment to manage the whole system.

#### To be done

- A more appealing website. It's not a must, but can be improved in several ways to make the user experience better.
- Realm to include
  - Full functionality about users data related to attempts to solve the problems
  - Functionality of DAO component.
  - Unit testing of the whole realm.
- In relation to the API
  - Adaption to run the code via blockchain instead of `gno test` to calculate the gas cost of the user solution.
  - Whole unit tests for the API
- Finish the Dockerfile to make the whole project executable in an AWS EC2 server.

After the whole project is fully functional, there will be a need to know the problems that are wanted to be added and which is the goal wanted to achieve with the realm for the DAO, but this can't be done until a DAO is defined.

#### Timeline and milestones

Splitting and giving a timelapse

- Finishing User features for realm (2-3 weeks)
- Finishing the DAO for ream (2-3 weeks)
- Full unit testing of the whole realm (2 months)
- Website enhacement (3-4 weeks)
- API fully functional with tests (3-4 weeks)
- Dockerfile and setup for AWS (2-3 weeks)

## Contributions or related work for gno.land (if applicable)

Currently I only have added [one PR to the GNO repository](https://github.com/gnolang/gno/pull/2677) as a result of adding a tool while working on this project. It hasn't been merged, but has been reviewed by @ajnavarro .
It worth to be mentioned that I have been reporting my progress on this project in [the developer calls of Wednesdays](https://github.com/gnolang/meetings/issues/37#issuecomment-2328217974).

## Why you and your team are well-suited for this project

Apart of my years of experience as developer, I think I'm very well-suited for this project essentially because I have been working on this project since some months ago, giving results most of the developer calls, demonstrating my commitment and proactive approach for it.
This also shows my already existing preparation to manage the tools and packages of GNO, helping me work faster when using GNO.

## Referrals or examples of past work

#### Examples of past work:

* [Hackatom 2022 project](https://github.com/gfant/Hackatom_2022)
* [Website for Huahua Community DAO](https://github.com/gfant/community-dao-website)
