# Ansible-Homelab

This is the repository I use to manage the services that I run in my homelab. It's small for now, but will hopefully grow in the future!

The repository is a set of Ansible `playbooks` that are used to deploy docker services from my [Dockerfile repo](https://github.com/Banshee1221/docker-homelab) (these might get merged in the future).

I figured I'd share!

To run it currently, point the inventory file to your to-be docker host, create the variables necessary (from the secrets.enc file... currently encrypted... TODO: add list of vars!) and run 

```bash
ansible-playbook -i inventory -e @secrets.enc docker-services.yml
```

Currently, this deploys:

- [LinuxServer.io SWAG](https://docs.linuxserver.io/general/swag) - Secure web application gateway as a reverse proxy
- [Tandoor](https://docs.tandoor.dev/) - A cookbook/recipe manager
- [Hauk](https://github.com/bilde2910/Hauk) - A live location sharing service
- [Signal-CLI](https://github.com/AsamK/signal-cli) - A commandline interface for Signal (used for sending myself alerts)