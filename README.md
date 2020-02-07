# revoke-github-token

An example for revoking the Actions-provided GitHub tokens (installation tokens) using the GitHub API.

The [`GITHUB_TOKEN` secret](https://help.github.com/en/actions/automating-your-workflow-with-github-actions/authenticating-with-the-github_token) can be accessed in the following contexts

* the [`secrets` context](https://help.github.com/en/actions/automating-your-workflow-with-github-actions/creating-and-using-encrypted-secrets#using-encrypted-secrets-in-a-workflow), via `secrets.GITHUB_TOKEN`
* the [`github` context](https://help.github.com/en/actions/automating-your-workflow-with-github-actions/contexts-and-expression-syntax-for-github-actions#github-context), via `github.token`.

### Workflow Invocation

```shell
curl -v -H "Authorization: token $TOKEN" https://api.github.com/repos/:owner/:repo/dispatches -X POST -d '{"event_type":"trigger"}'
```
