# safebrowse2
OpenWRT add-on to monitor browsing history and block sites by time of day for groups of devices

Consists of the following components:

1. OpenWRT code to:
  1. set up firewall rules to block particular sets of IP addresses at particular times of the day;
  2. set up cron jobs to qeury web service to see if there have been any changes to the rules
  3. submit useage statistics to a web service
2. The Web Service code:
  The web service responds to:
  1. GET queries about what ip addresses are included in groups corresponding to categories of web sites
  2. GET queries about what groups of ip addresses should be blocked at particular times
  3. POST queries submitting information about which hosts had active sessions in the firewall NAT table at particular times.
3. Web site for adding ip addresses to categories, and defining time of day rules for when different categories should be blocked for different users. The web site is a LAMP stack with a MySQL backend database.
4. There must be a 3rd party single sign on provider. A public Discourse instance is available for the public to use as an SSO destination, provided by the author.
