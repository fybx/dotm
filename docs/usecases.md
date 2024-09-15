# dotm docs

## usecases

A complete list of use cases that dotm covers is as follows:

### 1. initial setup (no local, no remote)

```bash
dotm init -l -u "remote_url"
nvim .config/dotm/deploy_list # whitelist folders and files here to backup
dotm backup
```

This will create and initialize a local repository with origin, then commit configuration, and push to remote.

### 2. new instance, old configuration (no local, remote exists)

```bash
dotm init -d -u "remote_url"
```

This will setup clone the local repository from remote, then deploy the configuration to place.

### 3. new instance, local configuration is newer than remote (no local, remote exists is out-of-date)

```bash
dotm init -u "remote_url"
nvim .config/dotm/deploy_list # whitelist folders and files here to backup
dotm backup
```

This is almost the same as the first usecase, however we don't deploy the remote configuration as soon as we clone to local.

