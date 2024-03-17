# KAPsNotes - React JS

This repository is for React JS notes by Kapil Sharma.

## Why these notes?

I last used react JS may be 4 years back and need to revise the concepts for a new requirements. I regret I didn't have any notes from the time I last used react and seem may be forgot most of the concepts. Fixing that mistakes, I decided to make react notes from scratch.

## Whom these notes are for?

> One line answer - for Kapil Sharma, for personal reference in the future.

However, if I'm making it from scratch, it should be helpful for others too. Considering this, I'll take some extra steps to include some of the very basic things. These notes should be good for:

- `New developers learnign React`. However, you must have some JavaScript knowledge.
  - Please note, I'm not a new developer, who is learning React for the first time. I'll try to make them beginner friendly, but if you believe I missed some crucial concept, feel free to create an [Issue](https://github.com/kapilsharma/kapsnotes-react/issues/new) or better send a PR.
- `Experienced developers`, as a `quick reference` of some of the concepts, if you forgot or need to revise.

Let's see both cases in a bit more details.

## New developer, learning React; What you can get from these notes? How to use them?

This is not a React book, explaining everything in details. `I personally believe and highly recommend` learnign by doing.

`But wait a minute`, won't it take a lot of time? `Well no`, not if you follow along with me on how I learn new technology. I believe in [80/20 rule](https://en.wikipedia.org/wiki/Pareto_principle)

> The Pareto principle (also known as the 80/20 rule, the law of the vital few and the principle of factor sparsity) states that for many outcomes, `roughly 80% of consequences come from 20% of causes` (the "vital few").
>
> -- [Wikipedia](https://en.wikipedia.org/wiki/Pareto_principle)

How does it apply to learning? Well, you need to understand what you need to learn. If we go in too much details, we definitely need a lot of time and believe me, for 80% of your project work, you will not need that deep level of knowledge. So my interpretation of 80/20 rule while learning new technology, programming language, framework, etc, is to learn enough so that you can complete 80% of the tasks of your project. For that, we need to learn 20%. We we need to learn all topics but without going too deep in the technology.

`Don't get me wrong`, we need deep level of knowledge (80%) for remaining 20% of the project. However, that 20% is software architecture, live release, optimization, security, advanced concepts, etc. They are improtant for us to go live but before we go live, we need to develop.

So learn enough so that you can start development of actual project. Once you start development, you will come across many things, keep learning them and you will soon be a master of the subject.

> You can't expect to learn swimming befor you enter the water.

Remember, no preparation can be as good as practical knowledge while developing a real world project.

I hope, now I'm a bit clear, we need to learn enough so that we can start  working on a project and later learning will keep going in parallel to actual development.

> So again, what you can get from these notes?

You will get the basics (20% of the subject), which will help you develop 80% of your project. Remaining 20% of project tasks, you will do them by learning while actually development of your project, as and when you reach there.

## How to go through these notes (Roadmap for new developers, learning React).

This is not a novel. You can't simply read it as a novel. 

If you want to follow my style and be capable of working on majority of your project:

- You need to code.
- You need to understand the basics not by reading, but by coding.
- You need to push yourself for the coding challenges.

> If you do it in my style, I believe in lot of code and just necessary theory, at least to start with.
> 
> Believe me, it worked very well for me over the years, while learning many new programming languages, frameworks, libraries and even principles like SOLID, DDD, Refactoring, Security, Live releases, Architecture, Best practices, and many more.
>
> The mantra is, `reward yourself`, boost your confidence. `We will start small`, get something wroking, `but we will not stop small`. Its continuous learnign process over the years but our immediate target is to be a professional developer (not masters), and start developing real world applications, in as little as a week or a couple of weekends.

These notes cover them all but you need to write code, not read it.

Once you are familiar, you can read the code to revise, while using these notes as cheatsheet. However, if you are reading it for the first time and don't already know react, you need to code. `Very important: This means typing the code, do not copy-paste my code on your editor.`

> `Remember:` There is no short-cut to the success. We can cut the learning time by smartwork (learning only what is necessary to start a real world project) but smartwork too needs smart thinking and hardwork.

**Next step:** Go to [Table of contents](./contents.md) but read them in order. you can also directly go to the next topic [Installation](./notes/installation.md)

## How to go through these notes (Experienced developer)

Well, if you need to revise or some sort of cheatsheet.

I'd recommend to go to [Table of contents](./contents.md) and select the topic you ant to revise. There also, you may skip the text and focus on headings and code. Read the text only if you do not understand the code.

## Getting the code

I'll make the versions of this repo in [Semantic Versioning](https://semver.org/). Versions format will be

> vX.Y.Z

`v` -> Constant, representing version<br/>
`X`, `Y`, `Z` -> Whole numbers

`X` -> `Major`: Represent Chapter (first level list) of Table of contents<br/>
`Y` -> `Minor`: Represent H2 level Topic in the Chapter<br/>
`Z` -> `Patch`: Section of code till that given point

All versions will be pushed to the git repo as branches. Whenever you need the code of a given point, just checkout from the branch like

`git checkout v2.1.0`

It will take the checkout of the branch that looks like during version `v2.1.0`

Version of the repo will be given in following format in the notes.

> ### Version: `v2.1.0`
> Some optional description, in case needed.

Whenever you notice that, you can checkout the repo on that version, to get the code exactly at that stage with following command

```bash
git checkout v2.1.0
```

If you don't want to clone the repo, you can also check the PR as all branches will merge with master only through a PR. PR title will be the version number.
