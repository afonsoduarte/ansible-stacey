# Ansible Stacey

Ansible playbooks for provisioning a server with Nginx, PHP, Dropbox and Stacey

Run after cloning:

    ansible-galaxy install -r requirements.yml

## Provisioning the server

    ansible-playbook -i hosts/[env] server.yml

## Deploying

    ansible-playbook -i hosts/[env] deploy.yml

## To setup Dropbox auto updates:

1. SSH as `web` user
1. Run Dropbox with `./.dropbox-dist/dropboxd`
1. Open URL that appears and authorise access
1. `dropbox stop`
1. Move content folder to `/srv/www/[website]/shared/content`
1. Symlink folder back to Dropbox, e.g. if folder was called `my-content-folder`:

        ln -s /srv/www/[website]/shared/content ~/Dropbox/my-content-folder

1. `dropbox start`
