Example Symfony app using reverse rsync strategy
===============================================

    $ git clone https://github.com/netiul/docker-sync-reverse-rsync-symfony-boilerplate.git
    $ cd docker-sync-reverse-rsync-symfony-boilerplate
    $ gem install --local docker-sync-with-rrsync.gem
    $ docker-sync-stack start

Wait for the containers to be started, then in separate terminals start watching the docker logs of the rsync containers.
    
    $ docker logs symfony-var-sync -f
    $ docker logs symfony-nodemodules-sync -f
    $ docker logs symfony-vendor-sync -f
    
Now perform the commands that will trigger the `reverse_rsync` strategies.
    
    $ docker exec -it docker-sync-reverse-rsync-symfony-boilerplate_symfony_1 /bin/bash
    $ composer install -o && npm install
    
I put a screen recording of these actions online: https://youtu.be/rgsTsIPaqBM
