# CiviCRM monitoring configuration pack for Shinken

CiviCRM (http://civicrm.org) is a great CRM (and more) tool for nonprofits and advocacy groups.
Shinken (http://shinken.io) is a great infrastructure monitoring tool.

## Usage

Your CiviCRM needs to have https://github.com/aghstrategies/com.aghstrategies.civimonitor installed and configured. 

Your Shinken needs to have check_civicrm.php (found in civimonitor extension) script up and running in plugins directory.

Just put this configuration in your Shinken configuration directory (like /etc/shinken/packs/civicrm) and apply configuration to your host as in example below. Don't forget to restart/reload Shinken.


```
define host {
   use             generic-host,civicrm
   host_name       <your host name>
   address         <your host address>

   # CiviCRM params
   _HTTP       <http|https>
   _SITE_KEY   <your CiviCRM site key>
   _API_KEY    <your API key>
   _CMS        <drupal|joomla|wordpress>

}
```

For more information on what can be monitored, make sure to check out https://github.com/aghstrategies/com.aghstrategies.civimonitor

Happy monitoring!
