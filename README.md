# What is this

This Program is an alternative version of the [Twitch Developer Rig](https://dev.twitch.tv/docs/extensions/rig).

Primarilly this works as a glorified Rest Client but handles the required [JWT generation](https://dev.twitch.tv/docs/extensions/building/#signing-the-jwt) or [App Access Token](https://dev.twitch.tv/docs/authentication/getting-tokens-oauth#oauth-client-credentials-flow) generation and maintance as needed.

Generally it should serve as a "test tool" and not used to manage a live extension, but you could, saves you writing your own Bits Product, or Extension Config Managment tool! *If you do so it's at your own risk*!

![First Launch Screenshot](screenshots/first_open.png)

Check out [more Screenshots](https://github.com/BarryCarlyon/twitch_extension_tools/tree/main/screenshots)

## Installation

This is an Electron App, so it maybe installed from the GitHub [releases tab](https://github.com/BarryCarlyon/twitch_extension_tools/releases).
It should also update from GitHub as new versions are released on GitHub. (Needs testing as I've never done Electron updates via GitHub)

It is Code Signed with the Publisher `Barry Carlyon`

You can download the latest version from here on GitHub under [releases](https://github.com/BarryCarlyon/twitch_extension_tools/releases)

## Data/Config Storage

Data is stored in the following location

> %appdata%/BarryCarlyonTwitchExtensionTools/

In the file `config.json`

Which follows the format:

```json
{
    "extensions": {
        ...
        "a_client_id": {
            "name": "Your Entered Name",
            "client_id": "",
            "extension_secret": "base 64 encoded secret",
            "user_id": "Twitch owner ID"
        },
        ...
        "a_client_id_with_secret": {
            "name": "Your Entered Name",
            "client_id": "",
            "extension_secret": "base 64 encoded secret",
            "client_secret": "a client API secret",
            "user_id": "Twitch owner ID",
            "access_token": "A recently generated App Access Token"
        }
        ...
    },
    "active": {
        "client_id": "Selected active Extension ClientID set to use",
        "version": "Selected Version to talk to"
    },
    "window": {
        "size": [ width, height ],
        "position": [ x, y ]
    }
}
```

⭐ Tip: If you open the Application and the window has gone missing, close the app, open `config.json` for editing and completely reset `"window"` to `{}` and then reopen the app, it'll reset to default display, top left.

## Supported Features

- [Get Extension Configuration Segment](https://dev.twitch.tv/docs/api/reference#get-extension-configuration-segment)
- [Set Extension Configuration Segment](https://dev.twitch.tv/docs/api/reference#set-extension-configuration-segment)
- [Set Extension Required Configuration](https://dev.twitch.tv/docs/api/reference#set-extension-required-configuration)
- [Send Extension PubSub Message](https://dev.twitch.tv/docs/api/reference#send-extension-pubsub-message)
- [Send Extension Chat Message](https://dev.twitch.tv/docs/api/reference#send-extension-chat-message)
- [Get Extensions](https://dev.twitch.tv/docs/api/reference#get-extensions)
- Simulation of the Extension Details page for the selected version of an Extension
- Test different Versions of an Extension against the API.

If a Key Sets Extension API Client Secret is Provided, alllowing the generation of [client credentials](https://dev.twitch.tv/docs/authentication/getting-tokens-oauth#oauth-client-credentials-flow)
- Convert UserName to UserID for various endpoints via [Get Users](https://dev.twitch.tv/docs/api/reference#get-users)
- [Get Extension Bits Products](https://dev.twitch.tv/docs/api/reference#get-extension-bits-products)
- [Update Extension Bits Product](https://dev.twitch.tv/docs/api/reference#update-extension-bits-product)

## Not Supported Features

- Extension View simulation, this might get explored but it's not gonna be as effective as actually testing on the Twitch Website itself (when in localtest).

## Notes

- Uses Electron to provide as a Desktop App
- Uses Bootstrap for primary layout
- Uses GitHub for update delivery and code management
- JWT tokens are generated _inside_ the App via [auth0/node-jsonwebtoken](https://github.com/auth0/node-jsonwebtoken), as apposed to "ClientSide" like [this example](https://barrycarlyon.github.io/twitch_misc/examples/extension_config/)
- A number of [sindresorhus](https://github.com/sindresorhus/) Electron Modules.

## Insomnia?

Basically this app is a "save my Extension configs" Insomnia-esque Rest Client. That wraps the main Extension functions in a handy Application. With some extra features!

[Insomnia](https://insomnia.rest/) is a Rest client. I have written a Plugin for Insomnia to aid with JWT generating inside Insomnia itself. You can find that [here on Github](https://github.com/BarryCarlyon/insomnia-plugin-twitch-extension-barrycarlyon)

## Warranty

If you break your extension from using this tool it's your own fault and the author(s) accept no responsbility for problems caused to your extension from using this tool. Granted the worse thing you might do is deprecate a bits product you actually needed.....

## License

This project is Licensed under [Do What The F*ck You Want To Public License](https://github.com/BarryCarlyon/twitch_extension_tools/blob/main/LICENSE), so Just Do What the F*ck you want to!

## Further Help with Twitch API

- [TwitchDev Documentation](http://dev.twitch.tv/docs)
- [TwitchDev Support Forums](https://discuss.dev.twitch.tv/)
- [TwitchDev Discord](https://link.twitch.tv/devchat)
- [TwitchDev Other Help](https://dev.twitch.tv/support)

[![TwitchDev Discord](https://discordapp.com/api/guilds/504015559252377601/embed.png?style=banner2)](https://link.twitch.tv/devchat)

## OMGLIEKWUT OHMYGOODNESS U SO MUCH HELP

Thank you for the help I want to give you beer/coffee money -> Check the Funding/Sponsor details
