# Google Domains DDNS Updater
Works well with `bash`.

Forked to add the ability to check current IP before updating. Google has implemented rate limits and they'll block you if you request to change too often, so it seems like a good idea. 

This script follows the [LSBInitScripts](https://wiki.debian.org/LSBInitScripts/).
You can update your IP address every few minutes using `cron`, or update it at boot time using `init`.

## Installation

*Make your [host information file](#example-of-host-information-file) first.*

`init`:
```bash
# Update IP at runlevel 0 1 2 3 4 5 6 (while booting, rebooting, shutdown, etc.)
$ update-rc.d update-ddns start 90 2 3 4 5 . stop 90 0 1 6 .
```

`cron`:
```bash
$ crontab -e

# Update IP for every 5 mins
*/5 *    *   *   *   /etc/init.d/update-ddns start
```

## Example of host information file
```json
{
	"amount": 3,
	"host1":
	{
		"hostname": "mysubdomain.mydomain",
		"username": "iVETU0O6r0CTNYdX",
		"password": "XsaMlfmzSU1dRrMg"
	},
	"host2":
	{
		"hostname": "mysubdomain2.mydomain",
		"username": "sUNeCRROUlnYbyDJ",
		"password": "afM95PIqWOGSNHHw"
	},
	"host3":
	{
		"hostname": "mysubdomain3.mydomain",
		"username": "tNCcjHOKHyVnHTg0",
		"password": "GiBeuNrU92JXLd1w"
	}
}
```

## Links
* [Google Domains Help - Dynamic DNS](https://support.google.com/domains/answer/6147083)
