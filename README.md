## Google Domains Dynamic DNS Updater
*Works with `bash`. Not works with `sh`, `ash`, `csh`, `zsh`..*

### Introduction

This script follows the [LSBInitScripts](https://wiki.debian.org/LSBInitScripts/).
You can update your IP address every few minutes using a `cron`, and can update at boot time using the `init`.

### Installation

*Before install, make your own [JSON](#json-example) first.*

Using `update-rc.d`:
```bash
# Update IP at runlevel 0 1 2 3 4 5 6 (while booting, rebooting, shutdown, etc.)
update-rc.d update-ddns start 90 0 1 2 3 4 5 6 .
```

Add line below using `crontab -e`:
```bash
# Update IP for every 5 mins
*/5 *    *   *   *   /etc/init.d/update-ddns
```

## JSON Example
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
