# component-release

  Node.js based git-release for use with component and npm

## Installation

    $ npm install component-release -g

## Usage

    $ component-release 0.0.0

## Features

  - Forces versions to be of the form `/^(\d+)\.(\d+)\.(\d+)$/` and won't let you publish with a version number that isn't of that form.
  - Won't let you publish with a version that doesn't match the version in `package.json` and `component.json` if those files are present.
  - Will automatically update the other of those files if you have updated one of them.
  - Will update both for you if you say yes when it asks you.
  - Will never 'update' to an older version
  - Won't let you publish an older version if a newer one exists (and is tagged)
  - won't let you publish if `component.json` or `package.json` exists but is not valid json.

  Provided you meet the requirements it will:

  - if a package.json is present and not marked private: `npm publish`
  - `git commit -a -m "Release 0.0.0"`
  - `git tag 0.0.0 -a -m "0.0.0"`
  - `git push --follow-tags`
