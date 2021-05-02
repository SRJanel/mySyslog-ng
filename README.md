mySyslog-ng
===========

A tool that I wrote to easily configure my syslog servers in front of my SIEM at home.
Still need to fix a few stuff though...


Allows to easily write configurations. For each configuration can:
- assign 2 templates "default" and "tls"
- choose the protocol of the incoming traffic
- choose a port for the incoming traffic
- apply a custom whitelist/lookup on hosts that send traffic (needs one otherwise traffic is sinkholed)
- choose on which servers each configuration should be applied (removes the configuration on target host if target is removed from deploy_hosts).

I personally used it with my gitlab internally (a CD pipeline is present in this repo; commit your changes made to the soc_stream.yml file and gitlab will auto-deploy to your hosts. I am also using a dev environment so that my configs are automatically applied in production only if they can be applied first in dev).

(Remember to change inventories/[dev/prod]/hosts files)
syslog-ng is supposed to be already installed on target servers (for now at least).

--> **c.f. soc_streams.yml for examples...** <--

## TODO
// TODO: Fix Bug: Ignore 'deploy_hosts' dict when deploying to dev environment..
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|-> Dev: deploy on single host (requires to use unique ports across all configurations)
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|-> Prod: all good, leave it as it is..
// TODO: Review README, write more stuff, give examples on how it works etc.
