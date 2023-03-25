# Changelog

## Mar 25 2023

- **Minor**
  - Added the option so save a post.
  - Added a way to get saved posts.
  - Added `has_saved` property to post object.
  - Added the option to archive a post.
  - Added the option to get archived posts.

- **Patch**
  - Fixed type checking for GluoIDs.
  - Fixed issue with a wrong model reference in `saved_posts()`.
  - Fixed the url of saved posts linking to `get_posts()`.

## Mar 21 2023

- **Minor**
  - Added `highest_permission()` function to the permission handler.
  - Added `is_valid_permission_collection` to permission handler.
  - Added promoting (mostly for testing not finalised)

- **Patch**
  - Fixed `@me` when getting user.
  - Fixed wrong `user` object when getting topics in `user_serializer`.
  - Fixed turning `visited_user.topics` into a list and not an object.

## Mar 20 2023

- **Minor**
  - Added 'topics' field to users.
  - Changed `/users/{query}` to `/user/{query}`.
  - Changed `/user/{query}` to default a `user_id` instead of a `username`.

- **Patch**
  - Fixed an issue in `settings.py`.
  - Fixed a wrong error message when getting posts.
  - Fixed a wrong object name for reactions in post_serializer.
  - Fixed throttling for authentication function.

## Mar 18 2023

- **Minor**
  - Added reaction counter to the post model.

- **Patch**
  - Fixed post liking
  - Fixed weird integer-type checking issue
  - Fixed post_topics not working

## Mar 11 2023

- **Major**
  - Added the option to delete an account.
  - Added `public_interactions` to the preference settings.

- **Patch**
  - Revamped some authentication functions.
  - Fixed wrong type preview in some errors.
  - Fixed logging in with inactive accounts.
  - Fixed weird bug when trying to activate an active account.

## Feb 09 2023

- **Major**
  - Added the option to set user-topics.

## Feb 08 2023

- **Major**
  - Added a list of followers.
  - Added a list of following.
  - Added the option to block and unblock.
  - Added the option to follow and unfollow.
  - Added the option to request a follow (private accounts only).
  - Added the option to accept and reject a follow (private accounts only).
  - Added the online list.

## Feb 05 2023

- **Major**
  - Added the option to like posts.
  - Added reaction creating.
  - Added the option to like reactions.
  - Added the option to get reactions under a post.
  - Added the option to get a specific reaction

## Feb 04 2023

- **Major**
  - Added the option to edit a post.
  - Added the option to delete a post.
  - Added the option to get random and trending topics.

## Jan 29 2023

- **Major**
  - Added post creating.
  - Added topic posts and following posts.
  - Added the option to get a specific post.
  - Added posts by a user.

- **Patch**
  - Revamped `request_handler.py` to be kinder on the eye.

## Jan 21 2023

- **Major**
  - Added registration for users.
  - Added logging in for users.
  - Added the option to change your password.
  - Added the option to change your email.

**DISCLAIMER**
The changelogs given below are for Gluo `v3`, the ones provided above are for Gluo `v4`.

## Jan 14 2023

- **Major**
  - Added profile posts, use `@me` as the topic.
  - Revamped moderation (regular users wont notice).
  - Removed /profile and /posts, they are now /user/{your-username} and /posts/{your-username}.

- **Minor**
  - Added embeds for gift links.
  - Added home and logout buttons to the landing pages for people that are logged in.
  - Revamped markdown, tagging and line breaks.
  - Fixed it so the previous buttons now continue at the bottom of the page.
  - Fixed /topics/home not working.
  - Fixed a bug with posts appearing private.
  - Fixed the redirect in /premium not working.
  - Fixed a bug were posts didn't appear on the profile.
  - Fixed pagination for followers and following.
  - Fixed specific posts giving an error in rare cases.
  - Fixed a bug with photos randomly rotating.

## Dec 19 2022

- **Major**
  - Added pagination to posts and comments in the hopes of speeding up the experience.
  - Added a "keep me logged in" button.
  - Revamped the way searching works.

- **Minor**
  - Revamped the homepage image.
  - Fixed insane loading times.
  - Fixed styling on the legal pages.
  - Fixed a bug with reactions not having a character limit.
  - Fixed broken popup on reaction sharing.
  - Fixed search command showing wrong results in some rare cases.

## Nov 30 2022

- **Major**
  - Added Gluo Premium.
  - Added a search bar.
  - Revamped the website UI (looks less basic now).

- **Minor**
  - Added captcha to signup.
  - Added tutorial for new users.
  - Added post embedding and anonymous post visiting.
  - Revamped the way the UI loads stylings sheets.
  - Revamped the code behind the UI to make is faster and smarter.
  - Fixed error with inactivated accounts.
  - Fixed reactions not working for private posts.
  - Fixed private posts not working in some rare cases.
  - Fixed a bug with markdown.
  - Fixed a bug with linebreaks in aboutmes.

## Oct 00 2022

- Things got added, fixed and Patched, but we forgot to log it.

## Sep 00 2022

- Things got added, fixed and Patched, but we forgot to log it.

## Aug 01 2022

- **Major**
  - Revamped the mobile UI to fit the PC design better.
  - Added light mode 🤢.

- **Minor**
  - Added forgot/reset-password.
  - Fixed liking, following and requests not working for mobile users.
  - Fixed THE profile picture bug for mobile users (a bug that has been around since March 14 this year).
  - Fixed an issue where topics wouldn't save.
  - Fixed the infinite scrolling bug that occured on PC.

## Jul 26 2022

- **Major**
  - Added reactions.
  - Added the followers list back.
  - Revamped the home page.

- **Minor**
  - Fixed some UI bugs.

## Jul 24 2022

- **Major**
  - Added liking and post deleting.
  - Added the home page.
  - Added specific topic pages.
  - Added specific post pages.

- **Minor**
  - Fixed one of the profile picture bugs.
  - Revamped the UI for followers and requests.

## Jul 22 2022

- **Major**
  - Added post creating.
  - Added the option to view your and others their posts.
  - Added requesting for private accounts.

- **Minor**
  - Revamped buttons and input fields.
  - Revamped the topics settings and the appearance of posts.

## Jul 20 2022

- **Major**
  - Fixed following, unfollowing and requesting.

- **Minor**
  - Fixed a bug where you could follow yourself.

## Jul 19 2022

- **Major**
  - Added the option to log out 😁.

## Jul 06 2022

- **Major**
  - Added profile settings.
  - Added topic settings.
  - Added following.

## Jul 05 2022

- **Major**
  - Added profiles and accounts.

**DISCLAIMER**
A lot happened before and during all these changelogs that got unregistered or just was irrelevant. The changelog shown here is the third iteration of Gluo and also the one that is currently publicly in use.
