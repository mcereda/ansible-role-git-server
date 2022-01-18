# Git server

Make a host a Git server.

## Requirements

None.

## Role Variables

Variable        | Type    | Default value        | Description
----------------|---------|----------------------|------------
authorized_keys | list    | `[]`                 | List of SSH keys authorized for connection
lfs             | boolean | `true`               | Enable LFS support
packages_apt    | list    | `["git", "git-lfs"]` | Packages to install using the APT package manager
packages_pacman | list    | `["git", "git-lfs"]` | Packages to install using the pacman package manager
user_dir        | string  | `/srv/{{ user_id }}` | Path to git user's home directory
user_id         | string  | `git`                | Username of the default git user
user_shell      | string  | `/usr/bin/git-shell` | Path to git user's shell

## Dependencies

None.

## Example Playbook

```yaml
- hosts: servers
  roles:
    - role: mcereda.git_server
      lfs: false
```

## License

MIT

## Sources

- [Setting up the server]

[setting up the server]: https://git-scm.com/book/en/v2/Git-on-the-Server-Setting-Up-the-Server
