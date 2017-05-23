# Virginia P. Moore OpenRefine Template

### Prefix

```
<?xml version="1.0" encoding="UTF-8"?>
<modsCollection xmlns="http://www.loc.gov/mods/v3" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:schemaLocation="http://www.loc.gov/mods/v3 http://www.loc.gov/standards/mods/v3/mods-3-5.xsd">
```

### Row Template

```
<mods xmlns="http://www.loc.gov/mods/v3" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:schemaLocation="http://www.loc.gov/mods/v3 http://www.loc.gov/standards/mods/v3/mods-3-5.xsd">
<identifier type="local">{{cells['identifier_file'].vlaue}}</identifier>
<titleInfo>
<nonSort>{{cells['title_initial_article'].value}}</nonSort>
<title>{{cells['title'].value}}</title>
</titleInfo>
<accessCondition type="use and reproduction" xlink:href="{{cells['rights_URI'].value}}">{{cells['rights'].value}}</accessCondition>
<name {{if(cells['rights_holder_name_authority'].value == 'naf', 'authority="naf" type="personal" valueURI="http://id.loc.gov/authorities/names/no00073285"', '')}}><namePart>{{cells['rights_holder_name'].value}}</namePart>
<role><roleTerm authority="marcrelator" valueURI="http://id.loc.gov/vocabulary/relators/cph" type="text">Copyright holder</roleTerm></role></name>
</mods>
```

### Row Separator

Leave this **blank**.

### Suffix

```
</modsCollection>
```