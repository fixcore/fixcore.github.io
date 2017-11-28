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

<div class="message">
	fx_events
</div>

>Here the custom server events are stored.

| Column Name | Type | Key | Null | Default | Comment
| ------ | ------ | ------ | ------ | ------ | ------ |
| id | int (10) | Yes | No | | Autoincrementable |
| title | varchar (100) | | No |
| description | text | | No |
| date_event_start | int (10) | | No |
| date_event_end | int (10) | | No |
| date| int (10) | | No |

**title**
* Name of the event

**description**
* Description of the event

**date_event_start**
* Start date of the event, _**you must use timestamp**_

**date_event_end**
* Final date of the event, _**you must use timestamp**_

**date**
* Publication date _**you must use timestamp**_

<div class="message">
	fx_news
</div>

>Here the news is hosted.

| Column Name | Type | Key | Null | Default | Comment
| ------ | ------ | ------ | ------ | ------ | ------ |
| id | int (10) | Yes | No | | Autoincrementable |
| title | varchar (100) | | No |
| image | varchar (100) | | No | new.jpg | assets/images/news |
| description| text | | No |
| date| int (10) | | No |

**title**
* Name of the news

**image**
* Name of the image file together with its extension. **_Unable to add external urls_**

**description**
* Description of the news
> The images must be lodged in this route assets/images/news

**date**
* Publication date _**you must use timestamp**_

<div class="message">
	fx_news_comments
</div>

>Here the comments of the news are saved

| Column Name | Type | Key | Null | Default | Comment
| ------ | ------ | ------ | ------ | ------ | ------ |
| id | int (10) | Yes | No | | Autoincrementable |
| id_new | int (10) |
| commentary | text | | No |
| date | int (10) | | No |
| author | int (10) | | No |

**id_new**
* ID of the news, it is taken from <span style="color:red">fx_news</span>

**commentary**
* Comment for the news

**date**
* Date of the comment. **_Timestamp must be used_**

**author**
* ID of the person who comments. It is taken from <span style="color:red">fx_users</span>

<div class="message">
	fx_news_top
</div>

>Here you will take the highlighted news

>It will only take 1 and is ordered from highest to lowest by ID

| Column Name | Type | Key | Null | Default | Comment
| ------ | ------ | ------ | ------ | ------ | ------ |
| id | int (10) | Yes | No | | Autoincrementable |
| id_new | int (10) | | No |

**id_new**
* Id of the news
>The id is the same as <span style="color:red">fx_news</span>

<div class="message">
	fx_questions
</div>

>Here secret questions are taken for registration

| Column Name | Type | Key | Null | Default | Comment
| ------ | ------ | ------ | ------ | ------ | ------ |
| id | int (10) | Yes | No | | Autoincrementable |
| question | varchar (100) | | No |

**question**
* The secret question.

<div class="message">
	fx_ranks
</div>

>Here you can edit all permissions

| Column Name | Type | Key | Null | Default | Comment
| ------ | ------ | ------ | ------ | ------ | ------ |
| id | int (10) | | No | | Autoincrementable |
| permission | int (10) | | No |

**id**
* ID user.
* It can be obtained from [account](https://trinitycore.atlassian.net/wiki/spaces/tc/pages/2130004/account#account-id)


**permission**
* 1 = Can join to AdminPanel

<div class="message">
	fx_shop
</div>

>Here everything that will be sold in the store is saved.

| Column Name | Type | Key | Null | Default | Comment
| ------ | ------ | ------ | ------ | ------ | ------ |
| id | int (10) | Yes | No | | Autoincrementable |
| title | varchar (100) | | No |
| description | text | | No |
| image | varchar (100) | | No | | assets/images/shop
| price_donate | int (11) |
| price_vote | int (11) |
| type | int (11) | | No | | 1-item or 2-query
| type_id | int (11) | | | | only if type = 1
| type_query | varchar (100) | | | | only if type = 2

**title**
* Product name

**description**
* Product description

**image**
* Name of the image file next to its extension. **_External URLs are not accepted._**
> The image must be saved in assets/images/shop

**price_donate**
* Value of the product with the donation currency

**price_vote**
* Value of the product with the voting currency

**type**
* 1 = If the product is an item
* 2 = If the product is a SQL query

**type_id**
* Here you will put the id of the item, it must exist in your world -> item_template
> Remember that to use this method you must type 1

**type_query**
* Here you should use the query with SQL syntax. Some shortcuts:
> Get account id: { fx_sess_id }
1. Query example: "UPDATE account SET name = 'newname' WHERE id = $id";

<div class="message">
	fx_shop_top
</div>

>Here you will take the best items from the store

>The system will take maximum 10 products and is ordered from highest to lowest by ID

| Column Name | Type | Key | Null | Default | Comment
| ------ | ------ | ------ | ------ | ------ | ------ |
| id | int (10) | Yes | No | | Autoincrementable |
| id_shop | int (11) | | No |

**id_shop**
* Product Id
> It can be obtained from [account](https://trinitycore.atlassian.net/wiki/spaces/tc/pages/2130004/account#account-id)

<div class="message">
	fx_slides
</div>

>Here you will take the best items from the store

>The system will take maximum 10 products and is ordered from highest to lowest by ID

| Column Name | Type | Key | Null | Default | Comment
| ------ | ------ | ------ | ------ | ------ | ------ |
| id | int (10) | Yes | No | | Autoincrementable |
| title | varchar (100) |
| image | varchar (100) | | No | image.jpg | assets/images/slides
| mobile_image | varchar (100) | | No | imagemobile.jpg | assets/images/slides

**title**
* Product Id
> Title of the Slide, it will appear.

**image**
* Name of the file along with its extension. **_External URLs are not accepted._**
> The image must be hosted in: **_assets/images/slides_**


**mobile_image**
* Image for small devices. Name of the file along with its extension. **_External URLs are not accepted._**
> The image must be hosted in: **_assets/images/slides_**

<div class="message">
    fx_slides
</div>

>Here you will take the best items from the store

>The system will take maximum 10 products and is ordered from highest to lowest by ID

| Column Name | Type | Key | Null | Default | Comment
| ------ | ------ | ------ | ------ | ------ | ------ |
| id | int (10) | Yes | No | | Autoincrementable |
| title | varchar (100) |
| image | varchar (100) | | No | image.jpg | assets/images/slides
| mobile_image | varchar (100) | | No | imagemobile.jpg | assets/images/slides

**title**
* Product Id
> Title of the Slide, it will appear.

**image**
* Name of the file along with its extension. **_External URLs are not accepted._**
> The image must be hosted in: **_assets/images/slides_**


**mobile_image**
* Image for small devices. Name of the file along with its extension. **_External URLs are not accepted._**
> The image must be hosted in: **_assets/images/slides_**

<div class="message">
    fx_tags
</div>

>This is an identical system to #battletag.

>The user will be assigned 4 random numbers and will work with his name # numbers

>For example: FIXCORE#1234

| Column Name | Type | Key | Null | Default | Comment
| ------ | ------ | ------ | ------ | ------ | ------ |
| id | int (10) | Yes | No |
| tag | varchar (100) | | No |

**id**
* ID of the account, is in [account](https://trinitycore.atlassian.net/wiki/spaces/tc/pages/2130004/account#account-id)

**tag**
* 4 Assigned random numbers

<div class="message">
    fx_users
</div>

>Here all countries are stored. In the registry you can choose the country of origin and take this table.

| Column Name | Type | Key | Null | Default | Comment
| ------ | ------ | ------ | ------ | ------ | ------ |
| id | int (10) | Yes | No |
| name | varchar (100) | | No |
| surname | varchar (100) | | No |
| username | varchar (100) | | No |
| email | varchar (100) | | No |
| question | int (10) | | No |
| answer | varchar (100) | | No |
| year | int (10) | | No |
| month | int (10) | | No |
| day | int (10) | | No |
| date | int (10) | | No |
| profile | varchar (100) | | No | default.jpg |

**id**
* ID of the account, is in [account](https://trinitycore.atlassian.net/wiki/spaces/tc/pages/2130004/account#account-id).

**name**
* First name - It will be taken from the registry.

**surname**
* Last name - It will be taken from the registry.

**username**
* Username - It will be taken from the registry.

**email**
* Email - It will be taken from the registry.

**question**
* Question - It will be taken from the registry.
> They are extracted from <span style="color:red">fx_questions</span>

**answer**
* Secret answer - It will be taken from the registry.

**year**
* Year of birth - It will be taken from the registry.

**month**
* Month of birth - It will be taken from the registry.

**day**
* Day of birth - It will be taken from the registry.

**date**
* Registration date - It will be taken from the registry.
> Timestamp must be used

**profile**
* Name of the image file
> It is obtained from assets/images/profiles

<div class="message">
    fx_users_annotations
</div>

>Here the account entries are saved

| Column Name | Type | Key | Null | Default | Comment
| ------ | ------ | ------ | ------ | ------ | ------ |
| id | int (10) | Yes | No | | Autoincrementable |
| iduser | int (10) |
| annotation | text | | No |
| date | int (10) | | No |

**iduser**
* ID of the person. It is taken from [account](https://trinitycore.atlassian.net/wiki/spaces/tc/pages/2130004/account#account-id)

**annotation**
* Annotation

**date**
* Date of the annotation. **_Timestamp must be used_**