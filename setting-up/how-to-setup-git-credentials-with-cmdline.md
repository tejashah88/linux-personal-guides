# How to setup Git Credential Manager

_Source_: https://github.com/git-ecosystem/git-credential-manager/blob/release/docs/credstores.md#gpgpass-compatible-files

1. Download Git Credential Manager from [here](https://github.com/git-ecosystem/git-credential-manager/blob/release/docs/install.md).

2. Configure it for the first time (if needed).

```bash
git-credential-manager configure
```

3. Set the default credential store to use "GPG/pass".

```bash
export GCM_CREDENTIAL_STORE=gpg
git config --global credential.credentialStore gpg
```

* Note: Only one of the commands are needed to run but I recommend running both.

4. Generate a new GPG key pair. It will prompt for your real name (can be your full name or similar identifier) and your email address.

```bash
gpg --gen-key
```

The User ID generated will be in the form of "[Real Name] <[Email]>" (e.g. Bob Smith <bob.smith@email.com>").

5. Initialize the credential store via `pass`, using the user ID generated from the previous step.

```bash
pass init <gpg-user-id>
```

6. (Optional) If you're planning to connect to this machine via SSH or similar TTY-based interface, add the following command to the end of your startup script (e.g. `~/.bashrc`).

```bash
export GPG_TTY=$(tty)
```