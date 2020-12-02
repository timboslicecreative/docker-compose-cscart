# docker-compose-cscart
Sanity saving docker configuration for running CSCART in development and production

## Why
As any developer that has tried to use CSCART, or even PHP with NGINX in both development and production environments may know, its an absolute nightmare of configuration. Setting up PHP and its modules is woefully cumbersome. CSCART has some hard coded limitations to working in a containerised environment, which are super fun to discover once you start deploying live to see that for instance Redis can only be used without a password, and was intended to be used on the same machine as PHP. Without agressive caching page render times are just long enough to put a round in the chamber and the barrel into your mouth. Utilising NGINX to serve the app requires you to volume map the entire CSCART source code which is ok in development but becomes unmanageable in production. 

Having to setup CSCART for some clients and demonstration purposes led to a full technical meltdown and frustration filled rants over why people persist with the abomination that is PHP. I left that steaming mess behind 5 years ago and had no plans to return, but hey, sometimes you gotta pay the bills right?

## What
Rather than address CSCART's problems with pathches and workarounds its best to lump it in the same container with NGINX and REDIS to force it to at least perform like a website launched in the 90's. Allowing at least the other services (db/mail/load balancing) to run in seperate containers. So here is a basic configuration for CSCART containerised using NGINX and REDIS.
