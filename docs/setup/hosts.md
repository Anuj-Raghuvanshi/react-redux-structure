# Local Setup - Hosts Configuration

In order to start development locally, you will need to modify your hosts file to map the development server's IP address (`127.0.0.1`) to a `command.kw.com` hostname.

This allows the console to properly authenticate as well as select what server environment the HTTP requests should be hitting. Use the chart below to determine the hostname you will need based on which server environment you want to hit.

| Environment | Server Base URL                       | Hostname                       |
| :---------- | :------------------------------------ | :----------------------------- |
| Dev         | `https://dev-kong.command-api.kw.com` | `local-dev.command.kw.com`     |
| QA          | `https://qa-kong.command-api.kw.com`  | `local-qa.command.kw.com`      |
| Prod        | `https://kong.command-api.kw.com`     | `local.command.kw.com`         |
| Connect     | `http://18.232.152.200`               | `local-connect.command.kw.com` |

> Most of the time, you should be developing on the **QA** environment unless you are working with an API that has not yet been deployed to QA.

The following line should then be added to your computer's host file:

```bash
127.0.0.1            HOSTNAME_FROM_TABLE
```

### Mac

1.  Open a new **Terminal**
1.  Run `sudo nano /etc/hosts`
1.  Enter your password as necessary
1.  Add the above line and save

### PC Instructions

1.  Navigate to `C:\Windows\System32\drivers\etc`
1.  Open the `hosts` file with any editor
1.  Add the above line and save
