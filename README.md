yvr-conf-free
=============

A node.js server that gathers the Mozilla YVR conference room FreeBusy information in an effort to display the conference rooms that are currently available for use. You can see a working example at:

* https://yvr-conf.paas.allizom.org/

Getting Started
=============

    npm start

Endpoints and API
=============

* Main Widget
  * http://0.0.0.0:3002/
* All Rooms and related Free / Busy information
  * http://0.0.0.0:3002/api/rooms
* Only rooms currently busy
  * http://0.0.0.0:3002/api/rooms/busy
* Only rooms currently free
  * http://0.0.0.0:3002/api/rooms/free

( NOTE: currently busy and free also includes a 5 min start time 'fuzz' where a room will be included if it is about to become free or busy )

Screenshot
=============

http://cl.ly/image/0C0k0x0Q2I2g

YVR Supported Conference Rooms
=============

* Siwash : yvr-2a
* Buntzen : yvr-2b
* Deep Cove : yvr-2c
* Lighthouse : yvr-2d
* Crazy Raven : yvr-2e
* Wreck : yvr-2f
* Dinky Peak : yvr-2g
* Adanac : yvr-2h
* Whytecliff : yvr-commons

Zimbra ICS Calendar URL Format:

    https://mail.mozilla.com/home/$EMAIL/Calendar?fmt=ifb&date=$DATE

Where `$EMAIL` = conf room email AND `$DATE` = moment.format("YYYYMMDD")


Deployment at Mozilla YVR
=============

*This will only apply for folks that have Mozilla LDAP accounts*

To deploy to the Mozilla PaaS, you will first need to be a member of the YVR group. If you're not, feel free to ping cturra for access.
With access (and the stackato client), run the following commands to login and join the group:

```
  stackato target api.paas.allizom.org
  stackato login <email>
  stackato group yvr
```

From this point, you can deploy normally :)
