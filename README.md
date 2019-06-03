# RemoteHub

RemoteHub is a **proof-of-concept** extension that allows for opening a remote [GitHub](https://github.com) repository as a workspace. Experimental code search and language services (go to definition, go to implementation, hovers, find references, etc) are provided by [Sourcegraph](https://sourcegraph.com) and will only work on public repositories that are enabled and supported by them.

NOTE: This extension is in the **very** early stages and is likely to have lots of bugs and only work in certain cases, so please keep that in mind. Also _please_ file GitHub issues for any questions, features, or issues. Thanks!

## Features

- Adds an _Open GitHub Repository..._ command (`remotehub.openRepository`) which allows you to search for a remote GitHub repository to open in the current window
- Adds an _Open GitHub Repository in New Window..._ command (`remotehub.openRepositoryInNewWindow`) which allows you to search for a remote GitHub repository to open in a new window
- Adds an _Add GitHub Repository to Workspace..._ command (`remotehub.addRepository`) which allows you to search for a remote GitHub repository to add to the current workspace
- Adds a _Clone GitHub Repository..._ command (`remotehub.cloneRepository`) which allows you to search for a remote GitHub repository to clone
- Adds a _Clone Current Remote Repository..._ command (`remotehub.cloneCurrentRepository`) which allows you to clone an opened remote GitHub repository
- Adds an _Open Current Remote Repository on GitHub..._ command (`remotehub.openCurrentRepositoryOnGitHub`) which allows you to open the current repository on GitHub
- Adds support for a `remotehub://` uri scheme, e.g. `remotehub://github.com/eamodio/vscode-remotehub` which can be saved into a workspace

## Requirements

### Generate a GitHub personal access token

> If you already have a token saved in the `github.accessToken` setting, you can skip this section as RemoteHub can use that token

RemoteHub requires a personal access token to authenticate to [GitHub](https://github.com)’s REST and GraphQL API. [Follow the steps](https://help.github.com/articles/creating-an-access-token-for-command-line-use/) in the GitHub guide, enabling the following scopes:

![Generate Token](https://raw.githubusercontent.com/eamodio/vscode-remotehub/master/images/generate-token.png)

Copy the generated access token to your clipboard and paste it into the input box or into your `settings.json` as follows:

```json
    "remotehub.githubToken": "<your-token-here>"
```

### Enabling File and Text Search

RemoteHub requires the use of proposed (read: experimental) APIs to provide both file and text search within VS Code.

To enable search:

- Set `"remotehub.insiders": true` in your settings
- Restart and run VS Code with the the following command line switch: `--enable-proposed-api eamodio.remotehub`

## RemoteHub Settings

| Name                    | Description                                                                                                                                                    |
| ----------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `remotehub.githubToken` | Specifies the GitHub personal access token to use for authentication with the GitHub GraphQL API                                                               |
| `remotehub.insiders`    | Specifies whether to enable experimental features                                                                                                              |
| `remotehub.search`      | Specifies the remote service to use for repository search<br />`github` - use GitHub search (only filename search)<br />`sourcegraph` - use Sourcegraph search |
| `remotehub.outputLevel` | Specifies how much (if any) output will be sent to the RemoteHub output channel                                                                                |

## Contributors 🙏&#x2764;

A big thanks to the people that have contributed to this project:

- Per Persson ([@md2perpe](https://github.com/md2perpe)) &mdash; [contributions](https://github.com/eamodio/vscode-remotehub/commits?author=md2perpe)

And of course the awesome [vscode](https://github.com/Microsoft/vscode/graphs/contributors) and [sourcegraph](https://github.com/orgs/sourcegraph/people) teams!
