Forks of the [https://github.com/appfair/appcasks.git](https://github.com/appfair/appcasks.git) repository provide the ability to augment any app's entry in the [App Fair.app](https://www.appfair.app).

## Rationale

The [App Fair.app](https://www.appfair.app) uses the Homebrew Cask system to obtain information about the available apps. This includes download URLs, cryptographic checksums, and information on how to install and un-install the apps. However, Homebrew, by design, does not include any additional metadata about applications that it indexes.

The appcasks system is designed to provide a creator-driven system for providing additional catalog information for specific apps. This includes the app's icon, categories, extended descriptions, screenshots and screencasts.

## Usage

If you are the vendor of an app that is accessible through App Fair.app and would like to provide an enhanced catalog entry for your app, follow these steps. **Note** your app must already be represented in the [Homebrew Casks catalog](https://formulae.brew.sh/cask/). If it is not, [start here](https://docs.brew.sh/Acceptable-Casks) to get it added.

1. Find your app's `token` and `homepage` by searching in the [Homebrew Casks catalog](https://formulae.brew.sh/cask/). For example, for the "iTerm2" app at [https://formulae.brew.sh/cask/iterm2](https://formulae.brew.sh/cask/iterm2), the `token` is "iterm2" and the `homepage` is "https://www.iterm2.com/".
2. Create a GitHub organization. It can be named anything, but you may want it to be similar to the app creator's name. You can re-use an existing organization if you have one, provided you can verify the homepage in the next step.
3. Add a verified domain for your organization that exactly matches the `homepage` for the cask and set the homepage to be the organization's public home page in GitHub. This homepage must appear is "verified" when displayed by GitHub in order for the app metadata to be accepted by the App Fair.
4. Fork this repository into your organization.
5. Go to the **Releases** page for your `appcasks` fork. 
6. Create a new release with a tag whose name exactly matches the token for the app your are adding information for.
7. Add an "AppIcon.png" image for your app – this will show up as the thumbnail for your app's entry in the App Fair catalog.
8. Add a "README.md" file with the metadata for your app. The contents should be formatted as per the [App Fair guide](https://www.appfair.net/#how-can-i-set-the-description-of-my-app-in-the-app-fair-catalog).
9. Add screenshots for your app, ideally in both dark and light modes, with the filenames structured as per the [App Fair screenshots naming conventions](https://www.appfair.net/#app-screenshots).
10. If your organization has multiple apps, repeat the previous 4 steps with the token name for the other apps. A single repository can have up to 25 associated app tokens.

Provided that your organization's homepage matches is verified with GitHub, your app's new metadata will appear when the catalog is next generated, which typically happes at least once an hour. Refresh the catalog in `App Fair.app` and search for your app, and once the catalog has been re-built your app's enhanced catalog information should appear in the form of an extended app description, an app icon, and screenshots.

