# mw-cron [INCOMPLETE]
Mutt Wizard automatic mail syncing wizard

Note: This fix requires `pinentry-dmenu` or `pinentry-bemenu`.

## Manual setup
1. Patch the mailsync script
```sh
# patch -u /usr/bin/mailsync mailsync.patch
```
2. Copy the `mw-set` script into `~/.local/bin`.
3. Make mw-set run when your graphical environment is started (depends on your system).
4. Add subfolders to the password commands in your msmtp/config and mbsync/config (from `pass x` to `pass automail/x`).
5. Generate a gpg key called email (don't use a password with illegal characters).
6. For each email password saved in your password store, create a password entry (using the email key) in the subfolder automail. If your email address is `example@email.com` then do
```sh
PASSWORD_STORE_KEY="email" pass insert automail/example@email.com
```
7. run mutt-wizard to create the cron job.
```sh
mw -T
```
