# Getting started

---

**Intended readers:**  API client developers, Architects, API developers, Technical PO

---

The easiest way to explore how superface works is to learn how tall is Master Yoda. This tutorial will get you going and teach you how to integrate capabilities that are already in superface. 

If you want to learn how to add a new capability to superface, [continue here](https://www.notion.so/Adding-a-use-case-348bfe4fce65469aa1da0f4f9ad09696). 

To read about what superface is and how it works, [check out this article](https://www.notion.so/How-superface-works-and-what-is-it-good-for-47098c19b67d4f29b5521e21c540d753).

# 1. Download our sample project

We created a sample project, we will use to retrieve information about Star Wars characters. [Download it here.](https://github.com/superfaceai/cli/tree/main/fixtures/consumer/starwars)

If you already have a project and need some other capability rather than Star Wars character data, choose one at [https://superface.ai](https://superface.ai) and keep reading.

# 2. Install superface CLI

[https://github.com/superfaceai/cli](https://github.com/superfaceai/cli)

The following steps only need to happen once. If you have already installed superface, you can [skip them]().

*Some sentence to explain how cool is our CLI.* 

### Add superface repo to your npm config

To install this package, first add the GitHub superface repository to your npm config. Use your GitHub name as your login and generate a personal access token with at least the repo and read:packages permissions in Github to use as password:

```bash
npm login --scope=@superfaceai --registry=https://npm.pkg.github.com
```

### Install the CLI

Use one of the following commands:

```bash
# if using yarn
yarn global add @superfaceai/cli
# otherwise
npm install --global @superfaceai/cli
```

This concludes installing the CLI. Let's now setup the development environment. Repeat the following steps for each project where you want to use superface.

- Install OneSDK
- Install use-case(s) you want to use
- Program your (JavaScript / TypeScript) application using the superface OneSDK

**VSCode user?**
[https://github.com/superfaceai/language-client-vscode/releases](https://github.com/superfaceai/language-client-vscode/releases)
If you use Visual Studio Code and want to make your experience even better, we recommend installing our [VSCode plugin](https://github.com/superfaceai/language-client-vscode/releases).

# 3. Install OneSDK

[https://github.com/superfaceai/sdk-js](https://github.com/superfaceai/sdk-js)

---

OneSDK is where all the magic happens. With it you can program your application declaratively to select the provider(s) and invoke the use-case. OneSDK uses superface servers only to discover available providers for your use-case and prepare for the invocation. The actual invocation of your use-case is happening between your application and the selected use-case provider without any intermediaries! **Any data you might send to the use-case provider including any data returned are absolutely never send to Superface servers (or anywhere else).**

---

To install the package, first create `.npmrc` file in your project root and put the following line into it.

```bash
@superfaceai:registry=https://npm.pkg.github.com
```

Then authenticate to GitHub npm package registry. Use your GitHub name as your login and generate a personal access token with at least the `repo` and `read:packages` permission in Github to use as password:

```bash
npm login --registry=https://npm.pkg.github.com
```

After doing this, you should be able to install the package by calling:

```bash
yarn add @superfaceai/sdk
```

if you have other dependencies in your project that you haven't installed yet, don't forget to call `npm install` or `yarn install` to populate `node_modules`

# 4. Install Profile

Superface is all about use-cases (the tasks you want to do) and providers who can fulfill your use-case. Next let's install our use-case. Use-cases are formally written in `.supr` files we call profiles and each of them has its ID. 

In our case, it's `starwars/character-information`. To install the profile, run the following command in you project directory:

```bash
superface install starwars/characater-information
```

You can see that this command also scaffolds a superface file structure. If you are building a project and don't want to install any profile yet, you can achieve this by executing  `superface init`.

**Open questions**

- *CLI prompts to initialize new superface structure - shouldn't this be automatic? @Eduard Lavuš has a good point that the prompt is a nice check of the proper destination (user might realize he is installing profile to the wrong directory) but I would still consider doing this automatically...*

```bash
File 'super.json' has not been found.
? **Would you like to initialize new superface structure?** (Y/n)
```

- *We might temporarily "install" providers from here as well... `superface install <profileId> --providers <providerName>`*

# 5. Install Providers

With use-case and SDK installed, it is time to install providers. Similarly to profiles, each provider has its own ID - e.g. `swapi.dev`

```bash
superface provider:configure <swapi.dev>
```

This step creates a skeleton of necessary security scheme information for that provider. 

Information about both profiles and providers is stored in `../<yourproject>/superface/super.json`. 

[Learn more](https://www.notion.so/notion-www-notion-so-47098c19b67d4f29b5521e21c540d753-9e9bed6b741e4973b7fbdba6a22ac529) about superface file structure and how API authorization and parametrization work.

**Open questions**

- *This step is now unnecessary for the Star Wars demo as it does not require any authentication. However, we should explain this step to users as it is required to understand for the common superface usage...*
- *Let's either have our own swapi API where some authorization is required or some other mock API like that with one shared key to teach the user how authorization works... where/how should he enter their environment variables to make it work, where are the secrutity scheme information to be found, etc....*

    E.g. create a `.env` file, add variables described in the provider definition of the `super.json` and appropriate credentials as the values. 

    In our case, it could be  `"$SWMOCKAPI_ACCESS_TOKEN"= 1234567890xxx` ,

# 6. Use SDK

### 3 or 2 lines of code

*For consumer flow, let's primarily describe the **Typed** use, add link to untyped as a secondary use and briefly describe what is typed vs. untyped in superface.*

- 3 lines of code (later 2 when Stephen's vision is deployed)
- see [Consumer flow foundations](https://www.notion.so/Consumer-flow-foundations-f4c36d37a7d248e286a73c2c5900d0f3) (3 lines),  [SDK Public API](https://www.notion.so/SDK-Public-API-f7384e8c06b64b34bc573d7c042ae1f8) (2 lines)

# 7. Run the app

`node app.js <character_name>` . Use Yoda, "Luke Skywalker" or any other character as <character_name>.

TODO

---

Now you know how to use superface in a nutshell. The best next step is to start building! If you want to take it step further and add a new capability to superface or are interested in deeper understanding of how superface works, this is the recommended reading:

[Adding a use-case](https://www.notion.so/Adding-a-use-case-348bfe4fce65469aa1da0f4f9ad09696)

[How superface works (and what is it good for)](https://www.notion.so/How-superface-works-and-what-is-it-good-for-47098c19b67d4f29b5521e21c540d753) 

[superface CLI](https://www.notion.so/superface-CLI-a2044016d9234d519704da0bec26f3bd) 

[OneSDK](https://www.notion.so/OneSDK-afba96f472dc468abc6954939f8174f3) 

# ...Next steps for this documentation

**Questions**

- Local vs. Online
- SF Ecosystem (file structure, super.json, etc.)
- Typed, untyped
- Playground?

# Authoring flow

WRITING

- How to write profiles and maps

PUBLISHING

- Ondra (jak se to deje na BE)
- Jak to pouzit v CLI
