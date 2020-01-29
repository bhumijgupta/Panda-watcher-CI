# Panda-watcher-CI

Panda watcher CI is a Github Action CI workflow script that complements [panda-portfolio](https://www.npmjs.com/package/panda-portfolio). It automates the task of building static html from config.json file.

## Introduction

Panda watcher CI is a complemetary script to [Panda-portfolio](www.npmjs.com/package/panda-portfolio). It automatically runs `npx panda-portfolio config.json`, builds static html from config.json, pushes it to the branch and requests page rebuild (in case of github pages).

## Features
* Autogenerate static html page when pushed changes to repo
* Requests gh-pages rebuild to deploy new site
* Easy to use and implement

## Usage
1. Generate Personal Authentication Token ([Why do I need this?](#Why-generate-PAT-token))
    1. In the upper-right corner of any page, click your profile photo, then click Settings.
    2. In the left sidebar, click Developer settings.
    3. In the left sidebar, click Personal access tokens.
    4. Click Generate new token.
    5. Give your token name `PAT_TOKEN`.
    6. Select repo scope.
    7. Click Generate Token.
    8. Click  to copy the token to your clipboard. For security reasons, after you navigate off the page, you will not be able to see the token again.

2. Go to repo where panda-watcher-CI is configured. Add PAT to repository secret.
    1. Go to Settings > Add new secrets
    2. Click on Add a new secret
    3. Give the title `PAT_TOKEN`, and paste the token from Step 2 in value
    4. Click on Add

3. Copy [`main.yml`](main.yml) to `.github/workflows` in the target repo.

4. You are ready to go.

## See demo
See demo on [https://github.com/bhumijgupta/bhumijgupta.github.io/](https://github.com/bhumijgupta/bhumijgupta.github.io/)

## Why generate PAT token
Panda-watcher-CI adds an additional commit to the repo. We add commit from a dummy account (panda-portfolio-ci@users.noreply.github.com). Github Actions does not run when additional commit is added from dummy account. This also does not trigger Github pages to rebuild the page. To rebuild the page we trigger Github pages API to rebuild the page, which requires the PAT token.

## License

![GitHub](https://img.shields.io/github/license/bhumijgupta/huffman-compression-library)

This library is licensed under MIT License. The license file can be found [here](LICENSE)

## Author

[![forthebadge](https://forthebadge.com/images/badges/built-with-love.svg)](https://forthebadge.com)

### Bhumij Gupta

![GitHub followers](https://img.shields.io/github/followers/bhumijgupta?label=Follow&style=social) [![LinkedIn](https://img.shields.io/static/v1.svg?label=connect&message=@bhumijgupta&color=success&logo=linkedin&style=flat&logoColor=white)](https://www.linkedin.com/in/bhumijgupta/) ![Twitter URL](https://img.shields.io/twitter/url?style=social&url=http%3A%2F%2Ftwitter.com%2Fbhumijgupta)

---

```C++
if(repo.isAwesome || repo.isHelpful){
    StarRepo();
}
```