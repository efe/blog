---
layout: post
title: "Password Manager: pass"
---

I was searching for a secure password manager. Instead of commercial ones ([1Password](https://1password.com/) and [Lastpass](https://www.lastpass.com/)), I'd like to have an independent, non-cloud and simple solution. Then, [pass](https://www.passwordstore.org/) shows up.

pass follows the beautiful [Unix philosophy](https://www.wikiwand.com/en/Unix_philosophy).

- Each encrypted password are stored in `~/.password-store`.
- Pushing the encrypted files to git is easy as `pass git push`.
- Clipping parameter `-c` is handy.
- Has plenty of extensions and clients.

I believe that we won't need password for each platform in the future. However, The future is not arrived yet. Up to that time, pass will be the optimal solution for me.
