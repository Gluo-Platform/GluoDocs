# Changelog

## May 10 2023

- **Major**
  - Added an endpoint to get all members of a group.
  - Added an endpoint to get a specific member of a group.

## May 08 2023

- **Major**
  - Added an endpoint to get all groups a user is member of.
  - Added an endpoint to leave a group.

## May 04 2023

- **Major**
  - Added an endpoint to delete a group.
  - Added inactive user removal.
  - Added an endpoint to join a group.

## May 03 2023

- **Major**
  - Added an endpoint to create groups.
  - Added a group permission handler.

## Apr 30 2023

- **Minor**
  - Added overview fields to general statistics.

- **Patch**
  - Fixed an issue with statistics.
  - Fixed an issue with topic serializers.

## Apr 25 2023

- **Patch**
  - Fixed an issue with a wrong topic reference in `create_post()`.
  - Fixed an issue with the absence of a date field in topic statistics.

## Apr 23 2023

- **Major**
  - Added an endpoint to get a group.

- **Patch**
  - Fixed an issue where archived and saved posts weren't ordered by creation date.
  - Fixed an issue with associated users when creating a notification in user-relations.  

## Apr 20 2023

- **Major**
  - Created group and user objects

- **Patch**
  - Fixed topic statistics (final time I hope)

## Apr 16 2023

- **Patch**
  - Fixed some issues that occured with statistics.
  - Fixed an issue with associated users in notifications.
  - Fixed an issue with a wrong method in `like_reaction()`.
  - Fixed some issues with error messages in `activate()`
  - Fixed an issue with a wrong field reference when updating topics.

## Apr 15 2023

- **Major**
  - Added general and topic statistic endpoints.

- **Minor**
  - Added invisible mode to user object
  - Added associated users to notifications

- **Patch**
  - Fixed an issue with the topic statistic gathering.
  - Fixed issue with datetime object in functions

## Apr 14 2023

- **Major**
  - Added an invisible mode.

- **Patch**
  - Fixed an issue where reactions were not filtered by creation date.

## Apr 13 2023

- **Major**
  - Added user statistics
  - Added post statistics
  - Added reaction statistics
  - Added moderation statistics

- **Patch**
  - Fixed wrong ID reference in user reactions endpoint.

## Apr 12 2023

- **Major**
  - Added user reactions

- **Patch**
  - Fixed delete reaction not returning error when reaction not found

## Apr 06 2023

- **Minor**
  - Changed the random topics endpoint.
  - Changed the trending topics endpoint (`/topics/trending` -> `/topics/popular`).
  - Changed the the preference settings to return a user object.
  - Added a popular user-topics endpoint.
  - Added a statistics endpoint.
  - Added the option to change your private `private` setting.

- **Patch**
  - Fixed random image rotations.
  - Fixed an issue where a wrong field was referenced in the topic object array function.
  - Fixed an issue with `public_interactions` in preference settings.
  - Fixed an issue where profile settings had the wrong status codes.
  - Fixed an issue where there was no url for the preference settings.

## Mar 31 2023

- **Minor**
  - Added avatar deletion when you change your avatar.
  - Added attachment deletion when a post gets deleted.

- **Patch**
  - Fixed a bug with user-topic fields.
  - Fixed a bug where video and audio attachments wouldn't get saved.
  - Fixed a bug with a field name issue in `update_topics()`.
  - Fixed a bug with an invalid status code for the login endpoint.
  - Fixed an issue with setting random user topics upon activation.
  - Fixed an issue with random topics.

## Mar 30 2023

- **Major**
  - Added an endpoint to search through users, posts and topics.
  - Added an endpoint to get your list of blocked users.
  - Added a usage count to the topic fields.

- **Minor**
  - Added blocked field to the user object.
  - Changed the way blocking people works.
  - Changed the way trending and random topics work.
  - Changed the topic-settings return object to return a user object.
  - Added file types to post objects.
  - Added visiting user to the reaction object.

- **Patch**
  - Fixed an issue with topic serialisation.
  - Fixed a bug with the post object when creating a new post.
  - Fixed a bug with status codes in post creation.

## Mar 29 2023

- **Major**
  - Added entity deletion as a moderation action.

- **Minor**
  - Added entity disappearance when it has too many reports.

- **Patch**
  - Fixed an issue with file types in attachments.
  - Fixed an issue with file names in attachments.
  - Fixed an issue where the post field on a user model counted invalid posts (archived/disabled).

## Mar 28 2023

- **Major**
  - Added the option to save attachments.
  - Added an endpoint to get user avatars.
  - Added an endpoint to get attachments.
  - Added option to refure a case.
  - Added moderation profiles.

- **Patch**
  - Fixed a bug with the notification serializer.
  - Fixed a bug with status codes for attachments being wrong.
  - Fixed a bug with checking for file types.

## Mar 27 2023

- **Major**
  - Added the option to claim a case.
  - Added the option to unclaim a case.
  - Added the option to file a case.
  - Added the option to verify a case.

- **Minor**
  - Changed url paths for getting cases.

- **Patch**
  - Fixed an error when a notification doesn't exist.
  - Fixed wrong names in moderation throttles.
  - Fixed forgetting no timestamps on notifications.

## Mar 26 2023

- **Major**
  - Added a way to get notifications.
  - Added a way to read a notification.
  - Added a way to delete a notification.
  - Added a welcome notification for new users.
  - Added the option to report a user.
  - Added the option to report a post.
  - Added the option to report a reaction.
  - Added a way to get unclaimed cases.
  - Added a way to get claimed cases.
  - Added a way to get pending cases.
  - Added a way to get verified cases.
  - Added the option to get a specific case.
  - Added a follow and request notifications.

- **Minor**
  - Changed post objects to provide large user objects.

- **Patch**
  - Fixed the error message for invalid passwords.
  - Fixed a small issue with random topics.
  - Fixed a small issue with trending topics.
  - Fixed weird bug when retreiving notifications.
  - Fixed checking for an archived property on reactions.
  - Fixed urls for user-relation related endpoints.
  - Fixed related names on case objects.
  - Fixed urls for moderation.
  - Fixed urls for moderation
  - Fixed function name in moderation serializer
  - Fixed issue with report models
  - Fixed user object in post objects.

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
  