
This ia a simple script that talks to a GitLab server using the
[GitLab API](http://doc.gitlab.com/ce/api/) to automate some project tasks from
the command line. It reads the configuration file named `~/.config/gitlab`. You
should specify there the GitLab server you want to use and your credentials.
Here is a sample config file:

```
[general]
default = gitlab.com
[gitlab.com]
token = xxx
base_url = https://gitlab.com/api/v3
```

If you are using gitlab.com you can find your private token in your
[account settings](https://gitlab.com/profile/account).

# Usage

cd to a git repository and call the script with one command argument. Commands
available currently are: `create_repo`, `project_id`, and `unprotect_branch`.

```
$ ./gitlabmatic --help
usage: gitlabmatic [-h] [--server SERVER]
                   [--log {DEBUG,INFO,WARNING,ERROR,CRITICAL}]
                   {create_repo,project_id,unprotect_branch} ...

positional arguments:
  {create_repo,project_id,unprotect_branch}

optional arguments:
  -h, --help            show this help message and exit
  --server SERVER       label for a Gitlab server
  --log {DEBUG,INFO,WARNING,ERROR,CRITICAL}
                        logging level
```

Run `./gitlabmatic <command> --help` for some help on an specific command.

