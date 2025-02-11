![workflow](https://github.com/gagoar/alohomora/workflows/alohomora/badge.svg)
[![codecov](https://codecov.io/gh/gagoar/alohomora/branch/master/graph/badge.svg?token=48gHuQl8zV)](https://codecov.io/gh/gagoar/alohomora)
[![Codacy Badge](https://api.codacy.com/project/badge/Grade/572336d13ec74669a40b7b26c23f58f5)](https://app.codacy.com/manual/xeroice/alohomora?utm_source=github.com&utm_medium=referral&utm_content=gagoar/alohomora&utm_campaign=Badge_Grade_Dashboard)
[![MIT License][license-shield]][license-url]

<!-- PROJECT LOGO -->
<br />
<p align="center">
  <a href="https://github.com/gagoar/alohomora">
    <img src="images/logo.png" alt="Logo" width="128" height="128">
  </a>

  <h3 align="center">Alohomora</h3>

  <p align="center">
    ✨A cli for AWS Systems Manager Parameter Store (ssm) 🔏
    <br />
    <a href="https://github.com/gagoar/alohomora#table-of-contents"><strong>Explore the docs »</strong></a>
    <br />
    <br />
    <a href="https://github.com/gagoar/alohomora/issues">Report Bug</a>
    ·
    <a href="https://github.com/gagoar/alohomora/issues">Request Feature</a>
  </p>
</p>

<!-- TABLE OF CONTENTS -->

## Table of Contents

- [About the Project](#about-the-project)
- [Built With](#built-with)
- [Getting Started](#getting-started)
- [Prerequisites](#prerequisites)
- [Installation](#installation)
- [Usage](#usage)
- [Contributing](#contributing)
- [License](#license)

<!-- ABOUT THE PROJECT -->

## About The Project

<p align="center">
  <a href="https://github.com/gagoar/alohomora">
    <img src="images/cast.png" alt="cast spell">
  </a>
</p>

Many libraries deal with parameter store secrets. However, I didn't find one that suits my needs, so I created this one. I wanted to develop a library that will solve all my needs while using secrets, including exporting the key/secrets to different formats

Here's why:

- Some solutions out there create their prefix to store keys, not leaving much flexibility when trying to migrate if needed.
- Exports were limited, not giving support to JSON output and possible others.

### Built With

- [aws-sdk](https://github.com/aws/aws-sdk-js)
- [ora](https://github.com/sindresorhus/ora)
- [cli-table3](https://github.com/cli-table/cli-table3)
- [dateformat](https://github.com/felixge/node-dateformat)
- [commander](https://github.com/tj/commander.js/)
- [cosmiconfig](https://github.com/davidtheclark/cosmiconfig)

<!-- GETTING STARTED -->

## Getting Started

Here is an example of how you may give instructions to set up a local project. You should follow these simple steps to get a local copy up and running:

### Prerequisites

- node 8 or higher
- AWS credentials to your account. ([more info here](https://docs.aws.amazon.com/sdk-for-javascript/v2/developer-guide/loading-node-credentials-environment.html))

### Installation

If you wish to use it as a stand alone utility:

```sh
npm -g install alohomora
```

It will make the command `alo` available in your command line

```sh
alo --help
```

If instead you would like to have it on a particular package.

```sh
npm install --only=dev alohomora
```

<!-- USAGE EXAMPLES -->

## Usage

Every command accepts several options via cli or via custom configuration [see configuration for more](#configuration)

### List secrets.

```sh
  alo list --prefix my-company/my-app
```

### Get secrets.

```sh
  alo list --prefix my-company/my-app
```

<!-- CONFIGURATION -->

## Configuration

alohomora can get configuration from several places:

### CLI options

If you are using it as a [global command](#installation), you can provide all the options via cli:

```sh
  alo list --prefix my-company/my-app --aws-region us-west-2  --aws-profile myCustomAWSProfile --environment production
```

for more details you can invoke:

```sh
  alo --help
```

### Custom Configuration

You can also define custom configuration in your package:

```json
{
  "name": "my-package",
  "alohomora": {
    "prefix": "my-company/my-app",
    "environment": "production",
    "region": "us-west-2"
  },
  "scripts": {
    "secrets": "alo export"
  },
  "devDependencies": {
    "alohomora": "^1.0.0"
  }
}
```

When the command is invoked it will take the key `alohomora` as configuration.

```bash
(my-package)$ npm run secrets
```

Custom configuration can be defined in many places, for more information check [cosmiconfig](https://github.com/davidtheclark/cosmiconfig)

<!-- ROADMAP -->

## Roadmap

See the [open issues](https://github.com/gagoar/alohomora/issues) for a list of proposed features (and known issues).

<!-- CONTRIBUTING -->

## Contributing

Contributions are what makes the open-source community such an amazing place to learn, inspire, and create. Any contributions you make are greatly appreciated **greatly appreciated**.

1. Fork the Project
2. Create your Feature Branch (`git checkout -b feature/AmazingFeature`)
3. Commit your Changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the Branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

<!-- LICENSE -->

## License

Distributed under the MIT License. See `LICENSE` for more information.

<!-- CONTACT -->

[![LinkedIn][linkedin-shield]][linkedin-url]

<p align="center">
  <a href="https://twitter.com/intent/follow?screen_name=shields_io">
      <img src="https://img.shields.io/twitter/follow/gagoar?style=social&logo=twitter" alt="follow on Twitter">
  </a>
  <a href="https://twitter.com/intent/follow?screen_name=shields_io">
      <img src="https://img.shields.io/twitter/follow/gagoar?style=social&logo=twitter" alt="follow on Twitter">
  </a>
</p>

<!-- MARKDOWN LINKS & IMAGES -->
<!-- https://www.markdownguide.org/basic-syntax/#reference-style-links -->

[contributors-shield]: https://img.shields.io/github/contributors/gagoar/alohomora.svg?style=flat-square
[contributors-url]: https://github.com/gagoar/alohomora/graphs/contributors
[forks-shield]: https://img.shields.io/github/forks/gagoar/alohomora.svg?style=flat-square
[forks-url]: https://github.com/gagoar/alohomora/network/members
[stars-shield]: https://img.shields.io/github/stars/gagoar/alohomora.svg?style=flat-square
[stars-url]: https://github.com/gagoar/alohomora/stargazers
[issues-shield]: https://img.shields.io/github/issues/gagoar/alohomora.svg?style=flat-square
[issues-url]: https://github.com/gagoar/alohomora/issues
[license-shield]: https://img.shields.io/github/license/gagoar/alohomora.svg?style=flat-square
[license-url]: https://github.com/gagoar/alohomora/blob/master/LICENSE.txt
[linkedin-shield]: https://img.shields.io/badge/-LinkedIn-black.svg?style=flat-square&logo=linkedin&colorB=555
[linkedin-url]: https://linkedin.com/in/gagoar
