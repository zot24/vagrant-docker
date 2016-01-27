Vagrant Docker
---

A vagrant machine provisioned by docker and docker-compose

# Install

```
vagrant plugin install vagrant-docker-compose
```

# Setup

```
config.vm.network :forwarded_port, :host => 4000, :guest => 9000
```
