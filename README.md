# StealthSend Frontend Components

Stealth desktop App for MacOs, Linux and Windows.
- Stealth Official @ Telegram @ Telegram: https://t.me/stealthsend

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
cd stealthsend-frontend-components
npm i
npm run serve
```

### Building

Builds for desktop apps are still in research state and this is yet to be documented.

### Deploying / Publishing

To deploy a new version of the kit, bump the patch tag and push (develop branch): 
```
git add .
git commit -m "XST-123 implemented bla"
npm version patch && git push && git push --tags
```

### Contributing

- use GitFlow because it is suitable for handling multiple versions of the same project
- when something on kit is updated and everything is ready to push on repository use

```shell
npm version patch && git push && git push --tags
```

### Links

- Stealth Official @ Telegram: https://t.me/stealthsend
- GitFlow: https://nvie.com/posts/a-successful-git-branching-model
