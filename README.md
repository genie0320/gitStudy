<!-- @format -->

# Git

git is developer's safety net.
Should used to.

## Basics

```
git add
git commit -m 'change log'

git branch <branch_name>
git switch <branch_name>

git merge <feature_branch_name> // Should be on main branch at this time.
    if there is conflict, fix and then try commit again.

```

## How to manage branchs.

1. [Git Flow](#gitFlow)
1. [Trunk-based](#trunkBased)

### [1. Git Flow](#gitFlow)

#### Concepts

![git-flow](git_flow.png)

- Master : Stores the official release history
- Develop : Serves as an integration branch for features.
  > This branch will contain the complete history of the project
- Feature : To develop new features that branches off the develop branch
  > ex. 'feature/feature_name'
- Release : Help prepare a new production release;  
  usually branched from the develop branch and must be merged back to both develop and master
- Hotfix : Also helps prepare for a release but unlike release branches, hotfix branches arise from a bug that has been discovered and must be resolved;
  > It enables developers to keep working on their own changes on the develop branch while the bug is being fixed.

#### Use case

1. Each developer should pull [develop],
   then make a [feature/..] from [develop] and start coding.
   When complete coding, give a 'pull request' to [develop].

1. Team leader can review the request and merge [feature/..] to [develop].

1. When [develop] ver. is ready to release, leader prepare [release/..] from [develop] to final test. if passed, [release/..] can be merged [master] and [**develop**]. ~~This is a new code base for the next release.~~
   > Because of this process, [master] have only release history, not all the history.
1. A bug is found after release, make [hotfix/...] from [master] and fix the bug. then merge to [master] and [develop]

#### Pros and cons

- Git-flow strategy is Suitable to strict release policy.

  > On the other hands, CI/CD can release with easy and fast but can be dangerous.

#### Ref.

- [지속적 통합/배포(CI/CD)를 위한 Git Workflow 전략](https://blog.ull.im/engineering/2019/06/25/git-workflow-for-ci-cd.html)

- [Gitflow workflow / atlassian](https://www.atlassian.com/git/tutorials/comparing-workflows/gitflow-workflow)

- [피그마에서 브랜치 잘 사용하기](https://brunch.co.kr/@designsystemguy/5)

### [2. Trunk-based](#trunkBased)

#### Concepts

![trunkbased][trunkbased.png]

[trunkbased.png]: trunkbased.png

A single branch called [trunk] and [feature/..] with very short life.

#### Pros and cons

- It's faster and easier to maintain than git-flow strategy.
- Need a automated test process to safe release. ~~Which hardly found in Korea.~~
- Need a stable development env. ~~Which hardly found in Korea, too.~~
- Need a well made peer review culture. ~~Which never can be at Korea.~~

#### Ref.

- [Trunk-Based Development](https://trunkbaseddevelopment.com/)
- [Git Flow에서 트렁크 기반 개발으로 나아가기](https://tech.mfort.co.kr/blog/2022-08-05-trunk-based-development/)
