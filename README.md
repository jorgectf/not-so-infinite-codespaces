# Infinite Codespaces

> Use GitHub Codespaces as if there was no timeout

## Disclaimer

Take into account that GitHub Codespaces is a paid feature. [More information](https://docs.github.com/en/billing/managing-billing-for-github-codespaces/about-billing-for-codespaces).

## Set up

* Fork this repository
* Go to the Actions tab and disable `Infinite Codespaces Executor for option_id` (... > Disable workflow)
* Go to Settings > Secrets > Actions and create:
  * `CODESPACES_PAT` with the value of a [Personal Access Token](https://github.com/settings/tokens) (Account settings > Developer settings > Personal access tokens > Legacy tokens) with `workflow`, `read:org` and `codespace` scopes. Configure the SSO for the token if you are planning to use organization-owned codespaces.
  * `SSH_PRIVATE_KEY` with the value of your __private__ SSH key (your GitHub account's private pair). If you do not have a public key configured in your GitHub account, go to the [SSH settings](https://github.com/settings/keys) and import one.
* Go to the [Codespaces settings](https://github.com/settings/codespaces) and set `Default idle timeout` to 240 minutes.

## Disable Codespace timeout

* Go to the Actions tab > `Infinite Codespaces Manager`
* Click `Run workflow` and fill the form.

<img width="329" alt="image" src="https://user-images.githubusercontent.com/46056498/172231658-bb358f80-ec54-482b-8430-a902d8f0590d.png">

  * `Self delete executor once the Codespace has been shut down` means that, if you manually shut down (or delete) the Codespaces instance, the Action will delete itself.
