# homelab

A Kubernetes based setup to run a home server.

## prerequisites

- A Kubernetes cluster running on the server.

## test bed

I'm using my Raspberry Pi 4 as my home server and all testing is done on it. 

- Raspberry Pi 4
- Ubuntu Server 22.04
- docker 20.10.12
- k3s v1.23.8+k3s1 (53f2d4e7)
- data stored on external drive - mounted at `/mnt/my-passport-drive`

## apps

### jellyfin

Jellyfin is a media server. Play all your local video content.

### wip - pihole (looking at other alternatives too)

Local DNS

### wip - nextcloud

File Sharing

## setting up your machine

You can either use [k3d](https://k3d.io/) to try out locally, or like I am, using a server.
I have k3s installed on my Raspberry Pi 4.

### k3s setup

Run the following to setup the cluster.

```bash
$ curl -sfL https://get.k3s.io | INSTALL_K3S_VERSION='v1.21.14+k3s1' sh -
```

Now you can run `terraform -chdir=iac plan` to check what's getting installed.

Finally, run `terraform -chdir=iac apply --auto-approve` to install everything.

