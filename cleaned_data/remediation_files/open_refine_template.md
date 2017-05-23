# Virginia P. Moore OpenRefine Template

### Prefix

```
<?xml version="1.0" encoding="UTF-8"?>
<modsCollection xmlns="http://www.loc.gov/mods/v3" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:schemaLocation="http://www.loc.gov/mods/v3 http://www.loc.gov/standards/mods/v3/mods-3-5.xsd">
```

### Row Template

```
<mods xmlns="http://www.loc.gov/mods/v3" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:schemaLocation="http://www.loc.gov/mods/v3 http://www.loc.gov/standards/mods/v3/mods-3-5.xsd">
<identifier type="local">{{cells['identifier_file'].value}}</identifier>
<titleInfo>
<nonSort>{{cells['title_initial_article'].value}}</nonSort>
<title>{{cells['title'].value}}</title>
</titleInfo>
<accessCondition type="use and reproduction" xlink:href="{{cells['rights_URI'].value}}">{{cells['rights'].value}}</accessCondition>
<name {{if(cells['rights_holder_name_authority'].value == 'naf', 'authority="naf" type="personal" valueURI="http://id.loc.gov/authorities/names/no00073285"', '')}}><namePart>{{cells['rights_holder_name'].value}}</namePart>
<role><roleTerm authority="marcrelator" valueURI="http://id.loc.gov/vocabulary/relators/cph" type="text">Copyright holder</roleTerm></role></name>
<typeOfResource>{{cells['item_type'].value}}</typeOfResource>
<originInfo>
<dateCreated encoding="edtf" keyDate="yes">{{cells['date_key'].value}}</dateCreated>
<dateCreated {{if(cells['date_qualifier'].value != 'ignore', 'qualifier="' + cells['date_qualifier'].value + '"', '')}}>{{cells['date_text'].value}}</dateCreated>
</originInfo>
<physicalDescription><form authority="aat" authorityURI="http://www.getty.edu/research/tools/vocabularies/aat/" valueURI="{{cells['form_URI'].value}}" >{{cells['form'].value}}</form></physicalDescription>
<relatedItem displayLabel="Project" type="host">
<titleInfo><title>{{cells['collection'].value}}</title></titleInfo>
<identifier>{{cells['collection_identifier'].value}}</identifier>
</relatedItem>
{{if(cells['name'].value != "IGNORE", '<name' + if(cells['name_authority'].value != "IGNORE", ' authority="' + cells['name_authority'].value +'"', '') + if(cells['name_uri'].value != "IGNORE", ' valueURI="' + cells['name_uri'].value +'"', '') + if(cells['name_type'].value != "IGNORE", ' type="' + cells['name_type'].value +'"', '') + "><namePart>" + if(cells['name'].value != "IGNORE", cells['name'].value, '') + "</namePart><role><roleTerm" + if(cells['name_role_uri'].value != "IGNORE", ' authority="marcrelators" valueURI="' + cells['name_role_uri'].value +'"', '') + "><roleTerm>" + if(cells['name_role'].value != "IGNORE", cells['name_role'].value, '') + "</roleTerm></role></name>", '')}}
{{if(cells['name2'].value != "IGNORE", '<name' + if(cells['name_type2'].value != "IGNORE", ' type="' + cells['name_type2'].value +'"', '') + "><namePart>" + if(cells['name2'].value != "IGNORE", cells['name2'].value, '') + '</namePart><role><roleTerm authority="marcrelators" valueURI="http://id.loc.gov/vocabulary/relators/isb">Issuing body</roleTerm></role></name>', '')}}

</mods>
```

### Row Separator

Leave this **blank**.

### Suffix

```
</modsCollection>
```