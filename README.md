Forks of the [https://github.com/appfair/appcasks](https://github.com/appfair/appcasks) repository provide the ability to augment any app's entry in the [App Fair.app](https://www.appfair.app).

## Rationale

The [App Fair.app](https://www.appfair.app) uses the Homebrew Cask system to obtain information about the available apps. This includes download URLs, cryptographic checksums, and information on how to install and un-install the apps. However, Homebrew, by design, does not include any additional metadata about applications that it indexes.

The appcasks system is designed to provide a creator-driven system for providing additional catalog information for specific apps. This includes the app's icon, categories, extended descriptions, screenshots and screencasts.

## Usage

If you are the vendor of an app that is accessible through App Fair.app and would like to provide an enhanced catalog for your app, follow these steps. **Note** your app must already be represented in the [Homebrew Casks catalog](https://formulae.brew.sh/cask/). If it is not, [start here](https://docs.brew.sh/Acceptable-Casks) to get it added.

1. Find your app's `token` and `homepage` by searching in the [Homebrew Casks catalog](https://formulae.brew.sh/cask/). For example, for the "iTerm2" app at [https://formulae.brew.sh/cask/iterm2](https://formulae.brew.sh/cask/iterm2), the `token` is "iterm2" and the `homepage` is "https://www.iterm2.com/".
2. Create a GitHub organization. It can be named anything, but you may want it to be similar to the app creator's name.
3. Add a verified domain for your organization that exactly matches the `homepage` for the cask and set the homepage to be the organization's public home page in GitHub. This homepage must appear is "verified" when displayed by GitHub in order for the app metadata to be accepted by the App Fair.
4. Fork this repository into your organization.
5. Go to the **Releases** page for your `appcasks` fork. 
6. Create a new release with a tag whose name exactly matches the token for the app your are adding information for.
