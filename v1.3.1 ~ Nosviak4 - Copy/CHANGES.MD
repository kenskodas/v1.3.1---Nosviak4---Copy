# Changes

Please note that this changelog was initiated with the release of v1.3.1, and it's possible that certain changes have not been documented.

## `v1.3.1 22/08/2023`

- Added

[COMMAND] `users changepw`: change the users password.
[COMMAND] `plans tokens`: Create redeemable plan tokens that users can utilize by entering the username `redeem` on the login screen.
[FUNCTION] `fakeSlaves`: emulate how real slaves act when connected to the CNC server.
[COMMAND] `users max_sessions=`: change the maximum number of sessions a user is allowed to have.
[COMMAND] `users newusers`: list of users who have not yet logged in for the first time.
[COMMAND] `users make_newuser`: promote a user to a newuser, forces them to change their password.
[CONFIG] `ongoing_cap`: Establish a constraint on the maximum number of ongoing attacks that can be in progress using a single method.
[CONFIG] `bypass_cooldown`: if the method follows the cooldown guidelines of a user.
[CONFIG] `funnel`: send attacks to 1 or more api endpoints.
[WEB] `APIs`: add, edit and delete API methods through the web dashboard.
[TERMINAL] `masking`: implemented password masking to protect sensitive information

- Changed

[COMMAND] `users roles`: improved functionality of the grabbing function.
[BRANDING] `login`: changed the default login screen.

Other important changes to the source code.
