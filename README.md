Symfony Standard Edition Skeleton
========================

Welcome to the Symfony Standard Edition, with all the Acme junk, routes and security configuration removed.
Perfect for cloning in an environment, updating with Composer and getting started on a new project.

Getting started with this Symfony Skeleton:
-------------------------------

First, fix app/logs and app/cache permissions using info from http://symfony.com/doc/current/book/installation.html

On linux web servers with sudo and setfacl, this means:
 rm -rf app/cache/*
 rm -rf app/logs/*
 APACHEUSER=`ps aux | grep -E '[a]pache|[h]ttpd|[_]www|[w]ww-data' | grep -v root | head -1 | cut -d\  -f1`
 sudo setfacl -R -m u:"$APACHEUSER":rwX -m u:`whoami`:rwX app/cache app/logs
 sudo setfacl -dR -m u:"$APACHEUSER":rwX -m u:`whoami`:rwX app/cache app/logs

On other linux systems with setfacl, find out what the apache user is and put it in the APACHEUSER var:
 rm -rf app/cache/*
 rm -rf app/logs/*
 APACHEUSER=
 setfacl -R -m u:"$APACHEUSER":rwX -m u:`whoami`:rwX app/cache app/logs
 setfacl -dR -m u:"$APACHEUSER":rwX -m u:`whoami`:rwX app/cache app/logs

Second, set up your Git repository correctly:
http://symfony.com/doc/current/cookbook/workflow/new_project_git.html

Then, create bundles and pages:
http://symfony.com/doc/current/book/page_creation.html
http://symfony.com/doc/current/bundles/SensioGeneratorBundle/commands/generate_bundle.html
