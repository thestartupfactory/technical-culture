[Back to README](../README.md)

# Development
Everything to do with how we like to develop software.  

## Tutorials
Check this for a variety of tutorials and resources you can use to bring your game to the next level.  

- Scala resources
  - [Ninety-Nine Scala Problems](http://aperiodic.net/phil/scala/s-99/)
    - Exercises 1-5, 7, 10, 12
    - Thanks @archena
  - [Scala for the Impatient](http://fileadmin.cs.lth.se/scala/scala-impatient.pdf)
    - Chapter 1-8 should give you a broad enough understanding
  - [Scala Style Guide](http://twitter.github.io/effectivescala/)

## Version Control System

- The Basics
  - We use `git`, it's a great tool.
  - Use [Github](https://github.com) too, it's wonderful.
- Branching
  - Readup on [Hubflow](https://datasift.github.io/gitflow/), this is how we like to work in teams.
- Pull requests (PRs) Basics
  - Always make PRs, as early as you can.
  - Fill in the description using the [template](#pr-template).
  - Comment on the ticket with a link to the PR.
  - Two thumb approval before a merge :+1: :+1:
  - Be helpful critical, no unhelpful criticism!
- Getting Reviews on PRs
  - Ping your PR in the relevant Slack channel
  - You are reponsible for it until merged or closed
- Rebasing and Merge Conflicts
  - Rebase onto `develop`
  - Do it often to your open PRs, about once per week
  - Solve conflicts where possible by rebasing back onto `develop`

## Style

- We have roots developing in Scala. So:
  - Keep it Functional
  - Immutable as standard
  - Mutable is a design choice
  - Event or actor driven
- Comment on your code where needed:
  - Code should be clear and readble by itself
  - Comments normally say _why_, not _what_

## PR Template

```
# [PROJ-22](https://thestartupfactory.pm.tool/browse/PROJ-22)

Some description for my PR.  
:warning: Some issue such as a pre-requisite PR for this feature.

### Checklist
- [x] xyz
- [ ] tested
- [ ] deployed
- [ ] ready for review/merge
```

[Back to README](../README.md)
