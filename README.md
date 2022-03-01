# Visual studio code server setup

Install visual studio code server as systemd daemon under linux. This run with your regular linux user.

## Requirements

* miniconda
* vscode

## Setup vscode

**Step 1**: Clone repo. 

```bash
$ cd ~
$ git clone https://github.com/adrianmarino/code-server-dashboard.git
$ mv code-server-dashboard code-server
$ cd code-server
```

**Step 2**: Create conda environment required to run vscode server.

```bash
$ conda env update -f environment.yml
```

**Step 3**: Copy service file user level systemd config path:

```bash
$ cp code-server.service ~/.config/systemd/user/
```

**Step 4**: Refresh systemd daemon with updated config.

```bash
$ systemctl --user daemon-reload
```

**Step 5**: Start service on boot.

```bash
$ systemctl --user enable code-server
```

**Step 6**: Start vscode server as systemd daemon.

```bash
$ systemctl --user start code-server
```
