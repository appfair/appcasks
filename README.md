Forks of the [https://github.com/appfair/appcasks.git](https://github.com/appfair/appcasks.git) repository provide the ability to augment a cask-based app's entry in the [App Fair.app](https://www.appfair.app).

## Rationale

[App Fair.app](https://www.appfair.app) uses the Homebrew Cask API to obtain information about the available catalog of apps. This metadata includes download URLs, cryptographic checksums, and information on how to install and un-install the apps. However, the central Homebrew catalog ([by design](https://docs.brew.sh/Acceptable-Casks#homebrew-cask-is-not-a-discoverability-service)) does not include any additional metadata about applications that it indexes.

The [appcasks](https://github.com/appfair/appcasks.git) repository is designed to fill this gap by enabling a creator-driven system for providing additional catalog information for individual apps. This includes the app's icon, categories & keywords, extended descriptions, screenshots and screencasts. It enables your app to be more easily discovered by users of App Fair.app, and provides an enhanced browsing experience to promote and inform potential users about your app's capabilities.

## Usage

If you are the vendor of an app that is already discoverable using App Fair.app and would like to provide enhanced catalog information for your app, follow these steps. **Note** your app must already be represented in the [Homebrew Casks catalog](https://formulae.brew.sh/cask/). If it is not, [start here](https://docs.brew.sh/Acceptable-Casks) to get it added, or you may consider using the [appfair.net](https://appfair.net) distribution network to freely create and distribute your apps.

1. Find your app's `token` and `homepage` by searching in the [Homebrew Casks catalog](https://formulae.brew.sh/cask/). For example, for the "iTerm2" app at [https://formulae.brew.sh/cask/iterm2](https://formulae.brew.sh/cask/iterm2), the `token` is "iterm2" and the `homepage` is "https://www.iterm2.com/".
2. Create a GitHub organization. It can be named anything, but you may want it to be similar to the app creator's name. You can re-use an existing organization if you have one, provided you can verify the homepage in the next step.
3. Add a verified domain for your organization that exactly matches the domain of the `homepage` for the cask by following [these instructions](https://docs.github.com/en/pages/configuring-a-custom-domain-for-your-github-pages-site/verifying-your-custom-domain-for-github-pages#verifying-a-domain-for-your-organization-site). Set this homepage to be the organization's public home page in GitHub. This homepage must appear as "verified" when displayed by GitHub in order for the app metadata to be accepted by the App Fair.
4. Fork this `appcasks` repository into your organization.
5. Go to the settings for your fork, select the `Pages` setting, and activate pages for the source `/ (root)` on `Branch: main`. GitHub pages must be enabled for the fork in order for the enhanced metadata to be included in the catalog.
6. Go to the **Releases** page for your `appcasks` fork and create a new release with a tag whose name matches the token for the app, prefixed with "cask-". For example, if your app's cask token is "foobar", you would create a release named "cask-foobar". The release description should be the description if your app as should appear in the catalog.
7. Add an "AppIcon.png" image for your app by adding it to the "Attach binaries" section. This image will show up as the thumbnail for your app's entry in the App Fair catalog.
8. Add a "README.md" markdown file to the app release with text describing the app in simple markdown (bold, italic, and links are supported, but not images or lists).
9. Add a "RELEASE_NOTED.md" markdown file to the app release with text describing the latest release. This file will need to be manually removed and re-added when new releases are issued when the release notes change. There is currently no required format or structure for the release notes.
10. Add screenshots for your app, ideally in both dark and light modes, with the filenames structured as per the [App Fair screenshots naming conventions](https://www.appfair.net/#app-screenshots).

If your organization has multiple apps, repeat the final 4 steps with the token name for the other apps. A single repository can have up to 25 associated app tokens.

Provided that your organization's homepage's domain matches the organizations's verified domain with GitHub and your have enabled pages for your fork, your app's new metadata will start showing up for users of App Fair.app after the next catalog generation (which typically happes at least once an hour). Refresh the catalog in `App Fair.app` and search for your app, and once the catalog has been re-built your app's enhanced catalog information should appear in the form of an extended app description, an app icon, and screenshots.

_Note_: if your app's homepage is itself a repository link on `github.com` itself, you can skip the domain verification step as long as you have forked the `appcasks` repo into the same repository as the homepage.
