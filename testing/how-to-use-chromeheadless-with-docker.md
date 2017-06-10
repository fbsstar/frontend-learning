# How To Use Chrome Headless With Docker

Unit Test is the first guard to prevent any regression. The good news is now we have chrome official support for [chrome headless](https://developers.google.com/web/updates/2017/04/headless-chrome).

# Guidelines

  - build a docker image with chrome (>59) installed, refer to [example](https://github.com/ebidel/lighthouse-ci/blob/master/builder/Dockerfile.headless)
  - lanuch the chrome headless by selected lanuch (now we use karma)
  
# Speical Note for running on ubuntu
Now ubuntu meet [docker issue](https://github.com/samuelli/bot-render/issues/2) but we could customize karma configure to add "--no-sandbox" as below

```json
browsers: ["DockerChromeHeadless"],
    "singleRun": true,
    "customLaunchers": {
      "DockerChromeHeadless": {
        "base": "ChromeHeadless",
        "flags": [
          "--no-sandbox",
          "--headless",
          "--disable-gpu",
          " --remote-debugging-port=9222",
        ]
      }
    }
```

# version
- version 1 written at 2017.6 -- this is current version
