# pulseaudio

This role installs [PulseAudio](https://www.freedesktop.org/wiki/Software/PulseAudio/) and creates a
[systemd](https://wiki.debian.org/systemd) service called `pulseaudio.service` in order to start
PulseAudio automatically.
If PulseAudio is already ran by the same user (see [`pulseaudio_user`](#role-variables)), then our
service will kill that instance prior to starting its own.

## Requirements

An apt based system like [Ubuntu](https://www.ubuntu.com/) or [Debian](https://www.debian.org/).

## Role Variables

| Name              |   Default    | Description                           |
| :---------------- | :----------: | :------------------------------------ |
| `pulseaudio_user` | `pulseaudio` | The user running `pulseaudio.service` |

The user `pulseaudio_user` is created if not already existent.
Also, it is added to the necessary groups for running PulseAudio.

## Example Playbook

```yml
- hosts: pulseaudio
  roles:
    - role: pulseaudio
      pulseaudio_user: stuvus
```
