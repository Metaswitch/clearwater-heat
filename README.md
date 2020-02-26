Project Clearwater is backed by Metaswitch Networks.  We have discontinued active support for this project as of 1st December 2019.  The mailing list archive is available in GitHub.  All of the documentation and source code remains available for the community in GitHub.  Metaswitch’s Clearwater Core product, built on Project Clearwater, remains an active and successful commercial offering.  Please contact clearwater@metaswitch.com for more information. Note – this email is for commercial contacts with Metaswitch.  We are no longer offering support for Project Clearwater via this contact.

# Clearwater Heat Templates

This repository contains templates for use with [OpenStack Heat](https://wiki.openstack.org/wiki/Heat) to deploy [Project Clearwater](http://www.projectclearwater.org).

`clearwater.yaml` is the top-level template, and depends on the other templates to create a network and Clearwater servers.

To use them, you must

-   have an [Ubuntu 14.04 cloud image](http://cloud-images.ubuntu.com/trusty/current/) imported into your OpenStack deployment
-   identify the external network in OpenStack that Clearwater should hang off, and find its network ID
-   create a DNS private key by running `head -c 64 /dev/random | base64 -w 0`
-   create the stack by running `heat stack-create clearwater -f clearwater.yaml -P "public_mgmt_net_id=...;public_sig_net_id=...;dnssec_key=..."`.

For further options, see the definition of the `parameters` block in `clearwater.yaml`.
