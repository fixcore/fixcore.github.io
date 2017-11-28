---
layout: page
title: Docs - Database.
permalink: database/
---

<div class="message">
	fx_chars_annotations
</div>

>Here the account entries are saved

| Column Name | Type | Key | Null | Default | Comment
| ------ | ------ | ------ | ------ | ------ | ------ |
| id | int (10) | Yes | No | | Autoincrementable |
| idchar | int (10) |
| annotation | text | | No |
| date | int (10) | | No |

**iduser**
* Character Guid. It is taken from [characters](https://trinitycore.atlassian.net/wiki/spaces/tc/pages/2129969/characters+table#characters(table)-guid)

**annotation**
* Annotation

**date**
* Date of the annotation. **_Timestamp must be used_**

<div class="message">
	fx_country
</div>

>Here all countries are stored. In the registry you can choose the country of origin and take this table.


| Column Name | Type | Key | Null | Default | Comment
| ------ | ------ | ------ | ------ | ------ | ------ |
| id | int (10) | | No | | Autoincrementable |
| country_code | varchar (2) | | No | '' | 
| country_name | varchar (100) | | No | '' |

**country_code**
* Unique code of the country.

**country_name**
* Country name