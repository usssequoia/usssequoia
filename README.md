# USS Sequoia
Website for the USS Sequoia - NCC1103 - The San Francisco chapter of [The Fleet](https://startrekthefleet.weebly.com), a Star Trek costuming fan group.

View the built website live here: https://usssequoiathefleet.com

## Development

* Dev log on [google docs](https://docs.google.com/document/d/1qUCTTprHwEdWrhSGv0eYOW0gDBdAEbo8eEwA3ohfHY4/edit?tab=t.0)
* A [HOWTO.md](HOWTO.md) file has some development notes in the form of FAQs.
    * This includes some general notes on `git` and how to find info on the theme.
* **Branches:**
    * **`Main`**: This branch is the primary development branch. 
        * New features in active collaboration can be worked on here prior to publishing.
    * **`Web`**: This is the branch that must be updated to publish changes to the hosted website.
        * A github action is configured to trigger a workflow to build and publish the website from the latest source content available in the `web` branch. The workflow is triggered any time an update is pushed to the `web` branch.
        * Assuming the build action completes without failures, this makes changes to this branch **live**, so take care when publishing content here.
    * *Any other branch*: Should be considered a draft for content or specific features in development. 
        * For example, other branches may be automatically created through a content management system.
        * Changes should be merged to both `main` (for development) and `web` (to publish). This can be accomplished by:
            * First: create a pull request from the *`other`* branch to the `web` branch. This will take the new post content in your branch and merge it into what is in the `web` branch, causing a rebuild of the site via github action trigger.
            * Second: create a pull request from the *`web`* branch to the `main` branch. This ensures that the latest content will be merged in with the development branch for future updates.

> [!IMPORTANT]
> Everything uploaded to this github project is ***publicly viewable online*** so:
> **do not under any circumstances** upload or push any personal information to the repository,
> including but not limited to private phone numbers, home addresses, or other personally
> identifying information unless consentual by all parties. It is difficult to fully remove information
> from the internet once it is made public! 
>
> If absolutely necessary to collect information (such as for polling or mailing-list sign-ups) this
> data should be kept off-site, in a separate non-public database, with encryption and access
> limited to such information need-to-know and deleted when no-longer needed.

## Acknowledgements

* This site incorporates the [Minimal Mistakes](https://github.com/mmistakes/minimal-mistakes) theme gem along with its dependencies, Copyright (c) 2013-2024 Michael Rose and contributors. Minimal Mistakes is distributed under the terms of the MIT License.

> [!NOTE]
> Star Trek and all related marks, logos and characters are solely owned by CBS Studios Inc. and
> Paramount Pictures. This fan club is not endorsed by, sponsored by, nor affiliated with CBS,
> Paramount Pictures, or any other Star Trek franchise, and is intended for entertainment and
> recreational purposes only.
