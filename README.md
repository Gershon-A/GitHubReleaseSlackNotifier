# Slack Release BOT

Send notifications to Slack about new releases.
> Required proper PR title format like: `<Jira issue number>: <PR title> @<pr author> (#<pr number>)`

## Inputs

This action requires the following inputs:

- `tag`: The tag of the release. This is a required input.
- `channel`: The Slack channel where the notification will be sent. This is a required input.
- `appName`: The name of the application. This is a required input. (if yhe service name and repo name is identical, you can use `${{ github.event.repository.name }}`)
- `jiraBaseUrl`: The base URL of your Jira instance. This is a required input and defaults to "<https://tricentis.atlassian.net>".
- `jiraProjectKey`: The key of the Jira project. This is a required input.
- `repoOwner`: The owner of the repository. This is a required input.
- `repoName`: The name of the repository. This is a required input.
- `webhook_url`: The URL of the Slack webhook. This is a required input.

## Usage

To use this action in your workflow, add the following step:

```yaml
- name: Slack Release BOT
  uses: Gershon-A/GitHubReleaseSlackNotifier@v1.0.0
  with:
    tag: ${{ github.ref }}
    channel: 'your-slack-channel'
    appName: 'your-app-name'
    jiraBaseUrl: 'https://your-jira-instance.atlassian.net'
    jiraProjectKey: 'your-jira-project-key'
    repoOwner: ${{ github.repository_owner }}
    repoName: ${{ github.repository }}
    webhook_url: ${{ secrets.SLACK_WEBHOOK_URL }}
```
