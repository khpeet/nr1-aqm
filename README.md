# Alert Quality Management (AQM)

## Usage

This application provides insight into alert hygiene and overall cleanliness of a given New Relic account's alert environment.

## Features
- Aggregated counts of issues and notifications across many accounts
- Drilldown KPIs per account
- Condition History - See the history of incidents that have triggered for a given policy/condition, as well as any recent changes, signal errors, and top offending entites.


## Getting Started
First, ensure that you have [Git](https://git-scm.com/book/en/v2/Getting-Started-Installing-Git) and [NPM](https://www.npmjs.com/get-npm) installed. If you're unsure whether you have one or both of them installed, run the following command(s) (If you have them installed these commands will return a version number, if not, the commands won't be recognized):

```bash
git --version
npm -v
```

Next, install the [NR1 CLI](https://one.newrelic.com/launcher/developer-center.launcher) by going to [this link](https://one.newrelic.com/launcher/developer-center.launcher) and following the instructions (5 minutes or less) to install and setup your New Relic development environment.


```bash
git clone git@github.com:khpeet/nr1-aqm.git
cd nr1-aqm
npm install
nr1 nerdpack:uuid -gf [--profile=<PROFILE>]
nr1 nerdpack:serve [--profile=<PROFILE>]
```

**Pro Tip: run `nr1 profiles:list` to see what profiles (accounts) are available to serve to.**

Visit [https://one.newrelic.com/?nerdpacks=local](https://one.newrelic.com/?nerdpacks=local), navigate to the Nerdpack, and :sparkles:

## Configuration
Update `config.json` located under `./nerdlets/` with your accountId, refreshRate (in milliseconds), and optional template dashboard name that will be linked to each account (if it exists in that account) within the Analytics tab. The refreshRate variable controls how often the Open* pages are refreshed automatically.

## Deploying this Nerdpack

Open a command prompt in the nerdpack's directory and run the following commands.

```bash
# To create a new uuid for the nerdpack so that you can deploy it to your account:
# nr1 nerdpack:uuid -g [--profile=your_profile_name]

# To see a list of API keys / profiles available in your development environment:
# nr1 profiles:list

nr1 nerdpack:publish [--profile=your_profile_name]
nr1 nerdpack:deploy [-c [DEV|BETA|STABLE]] [--profile=your_profile_name]
nr1 nerdpack:subscribe [-c [DEV|BETA|STABLE]] [--profile=your_profile_name]
```

Visit [https://one.newrelic.com](https://one.newrelic.com), navigate to the Nerdpack, and :sparkles:
