# Changelog
## Version 3.6.0
- [`Bot API 3`.`6` (February 13, 2018)](https://core.telegram.org/bots/api-changelog#february-13-2018)
    - Added `connected_website` attribute to the `Update` class.
- Added `parse_mode` attribute all stuff that has captions, in the bot functions and the sendable inline objects.
- Also added `supports_streaming` to `Bot.send_video(...)` and  `sendable.inputmedia.InputMediaVideo`.

## Version 3.5.2
- Added `username` and `id` property to the `Bot` class.
   This is basically the implementation used in [Teleflask](https://github.com/luckydonald/Teleflask) already, but calling it `id` and not `user_id` as it is a bot, not a user.
- Added `__str__` class, so that `str(bot)` displays as `Bot(username="luckybot", id=108721382)`

## Version 3.5.1
- Fixed `InputFileFromDisk`.
- Usage of `InputFile` with `file_blob` is now **deprecated**.
  Use `InputFileFromBlob` instead.

## Version 3.5.0
Updated official API changes of
- [`Bot API 3`.`4` (October 11, 2017)](https://core.telegram.org/bots/api-changelog#october-11-2017)
- [`Bot API 3`.`5` (November 17, 2017)](https://core.telegram.org/bots/api-changelog#november-17-2017)

## Version 3.3.1
- Removed doubled `WebhookInfo` classes at two different places. They are now the same.
- Fixed importing `Message` in `pytgbot.api_types.receivable.peer.Chat`.

## Version 3.3.0
- Updated Official API changes of [`Bot API 3`.`3` (August 23, 2017)](https://core.telegram.org/bots/api-changelog#august-23-2017)
    - Added new fields:
        + `peer.Chat.pinned_message`
        + `peer.User.is_bot`
        + `updates.Message.forward_signature`
        + `updates.Message.author_signature`
    - Removed fields:
        - `updates.Message.new_chat_member`
            - but `updates.Message.new_chat_members` still exists

## Version 3.2.0 __Not released__ `8eb2ff860af4ce6e44d3fcf5c012d8a070e046ee`
- Updated Official API changes of [`Bot API 3`.`2` (July 21, 2017)](https://core.telegram.org/bots/api-changelog#july-21-2017)
    - Stickers'n'stuff

## Version 3.1.1 __Not released__ `6654e962ce42e305be138efa90f9262098bf2b7d`
- fixed `send_video_note`, `send_video`, `send_voice`, `set_chat_photo` of `pytgbot.bot.Bot`.

## Version 3.1.0
- Updated Official API changes of [`Bot API 3`.`1` (June 30, 2017)](https://core.telegram.org/bots/api-changelog#june-30-2017)
    - Added new functions:
        - `pytgbot.bot.Bot.restrict_chat_member`
        - `pytgbot.bot.Bot.promote_chat_member`
        - `pytgbot.bot.Bot.export_chat_invite_link`
        - `pytgbot.bot.Bot.set_chat_photo`
        - `pytgbot.bot.Bot.delete_chat_photo`
        - `pytgbot.bot.Bot.set_chat_title`
        - `pytgbot.bot.Bot.set_chat_description`
        - `pytgbot.bot.Bot.pin_chat_message`
        - `pytgbot.bot.Bot.unpin_chat_message`
    - Updated `pytgbot.bot.Bot.kick_chat_member` function, added `until_date` parameter.
    - Updated `pytgbot.bot.Bot.send_invoice` function, `description` parameter now _optional_.
    - Updated parameter `chat_id` in game related methods to no longer allows string, so no more "@username".
        - `pytgbot.bot.Bot.send_game`
        - `pytgbot.bot.Bot.set_game_score`
        - `pytgbot.bot.Bot.get_game_high_scores`
    - Added `pytgbot.api_types.receivable.media.ChatPhoto`.
    - Updated `pytgbot.api_types.receivable.peer.Chat` to include the new fields:
        - `photo`
        - `description`
        - `invite_link`
    - Updated `api_types.receivable.peer.ChatMember`:
        - `status` field can now also be `"restricted"`
        - Added fields:
        - `until_date`
        - `can_be_edited`
        - `can_change_info`
        - `can_post_messages`
        - `can_edit_messages`
        - `can_delete_messages`
        - `can_invite_users`
        - `can_restrict_members`
        - `can_pin_messages`
        - `can_promote_members`
        - `can_send_messages`
        - `can_send_media_messages`
        - `can_send_other_messages`
        - `can_add_web_page_previews`
    - Removed documentation saying `pytgbot.api_types.sendable.inline.InlineQueryResultCachedDocument` was limited to sending only pdf-files and zip archives.
- Also now storing the incoming (decoded json) data in the `_raw` field of the object.


## Version 3.0.0
- Updated Official API changes of [`Bot API 3`.`0` (May 18, 2017)](https://core.telegram.org/bots/api-changelog#may-18-2017)
    - Added `pytgbot.api_types.receivable.VideoNote`.
    - Updated `pytgbot.api_types.receivable.peer.User` to include the new `language_code` field.
    - Updated `pytgbot.api_types.receivable.updates.Update` to include the new `shipping_query` and `pre_checkout_query` fields.
    - Updated `pytgbot.api_types.receivable.updates.Message` to include the new `video_note`, `new_chat_members`, `invoice` and `successful_payment` fields.
    - Added `pytgbot.api_types.receivable.updates.WebhookInfo`
    - Updated `pytgbot.api_types.sendable.inline.InlineQueryResultGif` to include the new `gif_duration` field.
    - Updated `pytgbot.api_types.sendable.inline.InlineQueryResultMpeg4Gif` to include the new `mpeg4_duration` field.
    - Added `pytgbot.api_types.sendable.payments.LabeledPrice`
    - Added `pytgbot.api_types.sendable.payments.ShippingOption`
    - Updated `pytgbot.api_types.sendable.reply_markup.InlineKeyboardButton` to include the new `pay` field.
    - Added `pytgbot.bot.Bot.delete_webhook` function.
    - Added `pytgbot.bot.Bot.send_video_note` function.
    - Documented that `pytgbot.bot.Bot.unban_chat_member` now works with channels too.
    - Added `pytgbot.bot.Bot.delete_message` function.
    - Added `pytgbot.bot.Bot.send_invoice` function.
    - Added `pytgbot.bot.Bot.answer_shipping_query` function.
    - Added `pytgbot.bot.Bot.answer_pre_checkout_query` function.


## Version 2.3.3
- Updated Official API changes of [`Bot API 2`.`3`.`1` (December 4, 2016)](https://core.telegram.org/bots/api-changelog#december-4-2016)


### Version 2.3.2
- Fixed failed version bump, which causing importing this package impossible.

### Version 2.3.1
- This is **not** Telegram `Bot API 2.3.1`!
- This version doesn't work. Use `2.3.2` instead.
- Fixed InlineQueryResultCachedSticker.


## Version 2.3
- Updated API changes of [`Bot API 2.3` (November 21, 2016)](https://core.telegram.org/bots/api-changelog#november-21-2016)

Changes I observed:
> Bot
>> **`answer_callback_query`**: added `cache_time`
>> **`edit_message_text`**: works for game messages too.
>> **`set_game_score`**: added `force`
>> **`set_game_score`**: added `disable_edit_message`
>> **`set_game_score`**: removed `edit_message`
>> **`set_game_score`**: `score` can be `0`. Now must be non-negative, before it must be postive.
>
> Classes:
>> **`updates.Update`**: added `channel_post`
>> **`updates.Update`**: added `edited_channel_post`
>> **`updates.Message`**: added `forward_from_message_id`
>
> Documentation:
>> **`Message`** ids are not called _unique_ no more.
>> **`CallbackQuery`** ids are not called _global_ no more.
>> **Inline Keyboard** Warnings removed.
>
> Might be a incomplete list, also have a look at the api changelog.

## Version 2.2.1

> Bugfix release

**Version 2.2.1a4**

- Fixed importing of `Game` in `Update.from_array(array)`.

**Version 2.2.1a3**

- Fixed importing of `InputFile*` after the package location change in [V2.2.0](#version-220).

**Version 2.2.1a2**

- Manually added placeholder class `pytgbot.api_types.receiveable.updates.`[`CallbackGame`](https://core.telegram.org/bots/api#callbackgame)

**Version 2.2.1a1**

- Fixed using wrong templates

## Version 2.2.0 ##
 - Moving `InputFile`, `InputFileFromDisk`, `InputFileFromURL` to `api_types.sendable.files.*` [#4](https://github.com/luckydonald/pytgbot/issues/4)
 - Implemented the changes from [`Bot API 2.2` (October 3, 2016)](https://core.telegram.org/bots/api-changelog#october-3-2016) ([gaming](https://core.telegram.org/bots/api#games) platform)
 - Improved templates, separated some stuff in the `Bot.do(...)` function for better subclassing. This will hopefully allow a subclass capable of returning infos, from an open webhook, later.

## Version 2.1.4 ##
- Reworked `InputFile`, `InputFileFromDisk`, `InputFileFromURL` internals.
    They now should handle input better. [#3](https://github.com/luckydonald/pytgbot/issues/3), [`luckydonald/bonbot` #131](https://github.com/luckydonald/bonbot/issues/131)

## Version 2.1.2 ##
- Fix: Also catching `TgApiException`s if `get_updates(..., error_as_empty=True)`

## Version 2.1.1 ##
- Renamed `get_updates(...)`'s `timeout` parameter to `poll_timeout`.
- Added `request_timeout` to `do(...)` method. Currently only `get_updates(...)` has that.

## Version 2.1.0 ##
- Renamed `pytgbot.api_types.receivable.media.File.download_url(token)` to `get_download_url(token)`
- Added a `pytgbot.bot.Bot.get_download_url(file)` method.

## Version 2.0.1 ## 
- Renamed `InputFileURL` to `InputFileFromURL`
- Added `InputFileFromDisk`
- `InputFile` is for buffers (strings) now

## Version 2.0.0 ##

Big overhaul:

- Real Objects for everything.
- Also most of this module can now be generated from the api website automatically, making updates a breeze.

## Version 1.0.1 ##
- Added ability to ignore network errors in `get_updates(...)` without raising a exception by setting `error_as_empty=True`.
  Useful in `for update in bot.get_updates(error_as_empty=True)` constructs. 
 
## Version 1.0.0 ##
- Added [Inline mode](https://telegram.org/blog/inline-bots) including [inlinefeedback](https://core.telegram.org/bots/inline#collecting-feedback).
  This should be [`Bot API 2.0` (April 9, 2016)](https://core.telegram.org/bots/api-changelog#april-9-2016).

## Version 0.0.0 ##
- First implementation
