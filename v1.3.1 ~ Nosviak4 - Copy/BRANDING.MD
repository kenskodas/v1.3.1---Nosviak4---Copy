# Branding

Are the extensive branding options feeling a bit overwhelming? I completely understand. To simplify things, I've provided all the branding files for you to modify. Each comes with a checkbox that you can mark as you make your way through the list. This approach is designed to streamline your experience and make things more manageable for you.

Just a quick note: as you accomplish these tasks, I suggest updating [0] to [1] as a personal marker of your progress.

## Checklist

1. `./assets/branding/prompt.tfx` [0]
   - This is visible right before the user's input area.
   - Here's a sample `prompt.tfx` you might find useful: `\x1b[0;38;2;50;255;255m<<user.$username>>\x1b[38;5;15m@\x1b[38;2;50;255;255m<<cnc()>>\x1b[38;5;15m:~# \x1b[97m`
   - And here's the default `prompt.tfx` you'll find on Nosviak4: `\x1b[0m \x1b[107m\x1b[31m <<user.$username>> ● <<cnc()>> \x1b[0m ►► \x1b[97m`

2. `./assets/branding/home_splash.tfx` [0]
   - This is visible whenever you login or run the `home` or `reset` commands
   - Below is a sample `home_splash.tfx` that you might find helpful:

     ```go
     <<clear()>>Hello <<user.$username>>
     ```

   - Here's the default `home_splash.tfx` you'll find on Nosviak4:

     ```go
     <?swash
         const $telegram = "https://t.me/NosviakCNC"
     ?>
     <<clear()>>\x1b[38;5;15mWelcome to <<cnc()>>, <<user.$username>>. Join our telegram: <<$telegram>>.
     <<spinner("greetings")>>
     ```

3. `./assets/branding/title.tfx` [0]
   - This is visible inside the title of the window of the SSH Client.
   - Below is a sample of `title.tfx` that you might find helpful: `\033]0; <<cnc()>> / Devices: [<<$fake_slaves>>] / Sessions: [<<session.total()>>] / User: [<<user.$username>>] / Expires: [<<time.until(user.$expiry)>>] / Slots: [<<db.ongoingUser(user.$username)>>/<<user.$conns>>] / @FB \007`
   - And here's the default `title.tfx` you'll find on Nosviak4: `\033]0; <<cnc()>> ~ Welcome <<user.$username>> \007`

4. `./assets/branding/command_not_found.tfx` [0]
   - This is visible whenever the user types an invalid command.
   - Below is a sample of `command_not_found.tfx` that you might find helpful: `(<<cnc()>>): Not found!`
   - And here's the default `command_not_found.tfx` you'll find on Nosviak4: `Command could not be found.`

5. `./assets/branding/command_access_denied.tfx`
   - This is visible whenever a user runs a command they can't access.
   - Below is a sample of `command_access_denied.tfx` that you might find helpful: `Missing permissions for that command.`
   - And here's the default `command_access_denied.tfx` you'll find on Nosviak4: `You lack authorisation to execute this command.`

6. `./assets/branding/attack_sent.tfx`
   - This is visible whenever an attack is launched **successfully**
   - Below is a sample `attack_sent.tfx` that you might find helpful:

     ```go
     Attack has been sent towards <<$target>> (At: <<time.unix(time.now(), "15:04:05 2006-02-01")>>)
     ```

   - Here's the default `attack_sent.tfx` you'll find on Nosviak4:

     ```go
     <?swash
         // lookups the target address
         const target = iplookup($target)
     ?> Method: <<$method>> 
     Target: <<$target>>
     Port: <<$port>>
     Time: <<$duration>>

     ASN: <<target.$asn>>
     Country: <<target.$country>>
     Org: <<target.$org>>
     ```

7. `./assets/branding/attack_failed.tfx`
   - This is visible whenever an attack is launched **unsuccessfully**
   - Below is a sample of `attack_failed.tfx` that you might find helpful: `Error occurred while sending attack`
   - Here's the default `attack_failed.tfx` you'll find on Nosviak4: `Error sending request to the API`

## Custom commands

Curious about incorporating personalized commands into your Nosviak4 build? By following this tutorial, you'll achieve success in achieving just that!

All custom commands are housed within the directory `./assets/commands/text/*`.

In the following guide, I will demonstrate how to craft a personalized command named `user-information`. This command serves the purpose of showcasing various details about a user, such as `maxtime`, `cooldown`, `conns`, `ongoing`, and `expiry`.

1. Establishing the metadata for a custom command involves storing essential command-related details that Nosviak4 needs for registration. Within Nosviak4's framework, there exist four default metadata fields: `name`, `description`, `permissions`, and `themes`.

The metadata structure for the command we are developing will resemble the following:

```toml
name="user-information"
description="displays information about your account"
permissions=""
themes=""
```

- `name`: Signifies the command's identifier, which is entered to activate it.
- `description`: Offers a concise yet comprehensive summary of the command's functionality.
- `permissions`: Encompasses a comma-separated compilation of permissions that grant access to execute the command (leave empty to allow all permissions).
- `themes`: Comprises a list of themes, separated by commas, within which the command is accessible (leave empty for all themes).

Now, let's proceed by including our `metadata-separator` along with the swash body. This can be achieved using the provided example:

```go
============================ START ============================
Username: <<user.$username>>
MaxTime: <<user.$maxtime>>
Cooldown: <<user.$cooldown>>
Conns: <<db.ongoingUser(user.$username)>>/<<user.$conns>>
Expiry: <<time.until(user.$expiry)>> (<<time.unix(user.$expiry, "2006-02-01")>>)
```

Now, it's time to delve into the complete example that showcases how the `./assets/commands/text/user-information.tfx` file will be structured.

```go
name="user-information"
description="displays information about your account"
permissions=""
themes=""
============================ START ============================
Username: <<user.$username>>
MaxTime: <<user.$maxtime>>
Cooldown: <<user.$cooldown>>
Conns: <<db.ongoingUser(user.$username)>>/<<user.$conns>>
Expiry: <<time.until(user.$expiry)>> (<<time.unix(user.$expiry, "2006-02-01")>>)
```

Wonderful, we've successfully crafted a fresh, custom command within Nosviak4!
