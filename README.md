<p align=center><img src=".github/logo.svg" alt="Macaw" /></p>

# Scalable email templates for node.js

Macaw is a suite of tools that helps you design and send transactional emails. It aims to solve the problems that usually occur at the intersection of design, copywriting and engineering.

**Macaw is:**

- A node.js package that helps you to use templates to send transactions emails
- A CLI tool that helps you structure and preview templates

**Macaw is _not_:**

- A Mailchimp-esque drag-and-drop email builder
- A email sending service

## Quick example

Some lines of code usually say more than any documentation could, so here's an optimistic example of how this library could be used:

```js
const macaw = require("@macaw-email/engine");
const sendgrid = require("@macaw-email/provider-sendgrid");

const mailer = macaw({
  provider: sendgrid({ apiKey: "aaaaa-bbbbbbb-ccccccc-ddddddd" })
});

const template = mailer.template("monthly-newsletter", {
  customerName: "Example Business",
  greeting: "Hi, Thomas!"
});

await template.send({
  to: {
    name: "Thomas Schoffelen",
    email: "thomas@schof.co"
  }
});
```

## Getting started

Quickly get up and running by executing this command in your project's root directory:

```shell
npx macaw init
```

This will:

1. Create a `emails` directory with an example template and layout file.
2. Add `@macaw-email/engine` to your package.json file.

Take a look at the files created in the `emails` directory, and use the documentation links below to learn what's next.

## Documentation

- [Templates and layouts]()
- [Email sending providers]()
- [Custom providers]()
