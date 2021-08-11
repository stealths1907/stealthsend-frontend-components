# Stealth UI Kit

Stealth desktop App for MacOs, Linux and Windows.
- Jira board: https://jira.barrage.net/projects/XSTDESKTOP
- Slack channel: https://wearebarrage.slack.com/archives/G01KQNE67PV

Main technologies:
- Vue (3.0.x)
- PostCSS (8.2.x)

### Prerequisites


```
└─ $ ▶ node -v
v12.18.2
```

```
└─ $ ▶ npm -v
6.14.5
```

### Initial configuration for running and developing

After cloning the repo from our git, do the following steps

Example:

```shell
cd stealth-kit
npm i
npm run serve
```

### Building

Builds for desktop apps are still in research state and this is yet to be documented.

### Deploying / Publishing

Deploys for desktop apps are still in research state and this is yet to be documented.

### Contributing

- use GitFlow because it is suitable for handling multiple versions of the same project
- reference Jira task in the commit message (e.g. "XSTDESKTOP-123 implement login")
- when something on kit is updated and everything is ready to push on repository use

```shell
npm version patch && git push && git push --tags
```

### Links

- Jira board: https://jira.barrage.net/projects/XSTDESKTOP
- Slack channel: https://wearebarrage.slack.com/archives/G01KQNE67PV
- GitFlow: https://nvie.com/posts/a-successful-git-branching-model
