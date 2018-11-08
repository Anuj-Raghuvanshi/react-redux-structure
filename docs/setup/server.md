# Local Setup - Starting Development Server

This article assumes that you have cloned this repository locally, installed all dependencies and [configured your hosts file](hosts.md).

From the root directory, run the following command:

```bash
npm start
```

Use the table below to determine your local development URL based on the environment you configured your [hosts file to map](hosts.md).

| Environment | Hosts File Hostname            | Local Development URL                      |
| :---------- | :----------------------------- | :----------------------------------------- |
| Dev         | `local-dev.command.kw.com`     | `http://local-dev.command.kw.com:8000`     |
| QA          | `local-qa.command.kw.com`      | `http://local-qa.command.kw.com:8000`      |
| Prod        | `local.command.kw.com`         | `http://local.command.kw.com:8000`         |
| Connect     | `local-connect.command.kw.com` | `http://local-connect.command.kw.com:8000` |

> The port number 8000 at the end of the URL is required!!

When you first access any of the above URLs, you will likely be redirected to `login.command.kw.com`. Follow the [authentication](authentication.md) instructions to access the application.
