Drakewell
=========

The web portal at https://drakewell04.drakewell.com/ seems to work with the supplied credentials. Unfortunatly the 'user Guide' link on the home page gives 'Access denied'.

These examples seem to work:

```
https://drakewell04.drakewell.com/datex2/datex2_predefinedlocations.asp?v=2.2&node=cambridge_jtms&key=644d6643127d494fad96f1a05357d1e0
https://drakewell04.drakewell.com/datex2/datex2_trafficdata.asp?v=2.2&node=cambridge_jtms&key=644d6643127d494fad96f1a05357d1e0
```

Based on 'Datex 2 & JSON API Information JTMS' document you might think

```
https://drakewell02.drakewell.com/npmatchv2/exports/a/locations.asp?group=cambridge_jtms&key=644d6643127d494fad96f1a05357d1e0
```

would also work, but it gives

```
{
    "FAIL": true,
    "data": {
        "message": "Access Denied"
    }
}
```

which suggests that I'd need a different key (and indeed in the examples there are seperate keys).

Extracting predefined locations from XML:
```
xmlstarlet sel -N d=http://datex2.eu/schema/2/2_0 -t -m '//d:predefinedLocationName' -m "d:values" -v "d:value" -n predefinedlocations.xml
```
