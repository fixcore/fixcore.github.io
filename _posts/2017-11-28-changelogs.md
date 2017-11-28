---
layout: post
title: "Changelogs"
quote: "Who is General Failure and why is he reading my hard drive?"
image: false
video: false
comments: true
---

## Forums

* New Database [fx_forum_comments](https://github.com/fixcore/BlizzCMS-DATABASE/commit/8ed52e81620d84e94055dd317a565bbfa8d1563f)

* The "create topic" button will now only be displayed if you are connected. [5967ac0](https://github.com/fixcore/BlizzCMS/commit/5967ac09a597b2d62a425b8de5d5bfbcdd8cb80b)

* The function "highlight and lock" in the forums is repaired (Now it will only be visible by STAFF people). [5967ac0](https://github.com/fixcore/BlizzCMS/commit/5967ac09a597b2d62a425b8de5d5bfbcdd8cb80b)

* In the topic now you will see correctly the amount of post that the author has created. [278ab10](https://github.com/fixcore/BlizzCMS/commit/278ab10231baf798f717f236e76550d2f6b75079)

* The posts are now organized in order of creation. [2b1dcf1](https://github.com/fixcore/BlizzCMS/commit/2b1dcf15288aa9774b49abd8e8343b4b3524aaa3)

* Now in the list of forums you will see the publications highlighted with another color. In addition they will always be in first place. [32b2abd](https://github.com/fixcore/BlizzCMS/commit/32b2abd6fdb850c42c32a7f745ae7f76ba77c62a)

* Now in the forums list the author will see a different color according to his range of GM. [32b2abd](https://github.com/fixcore/BlizzCMS/commit/32b2abd6fdb850c42c32a7f745ae7f76ba77c62a)

* Now the comment system works correctly [baebd68](https://github.com/fixcore/BlizzCMS/commit/baebd684eb741020b9f27ba9c534d30d715b42a9)

<div class="message">
You will have to reinstall the web for which the new database will be applied.
</div>

>If you do not want to reinstall the web, you can install it manually. Find it here: [8ed52e8](https://github.com/fixcore/BlizzCMS-DATABASE/commit/8ed52e81620d84e94055dd317a565bbfa8d1563f)

* Now the color of the letters will change if the author is GM. [9fc7442](https://github.com/fixcore/BlizzCMS/commit/9fc7442ebbe322b02ecf0c9542fc21e844dcc670)

<div class="message">
You can define the color of the letters in the configuration <strong>application/config/fixcore.php</strong> on line 33 
<strong>$config['staff_forum_color']</strong>
</div>

<div class="message">Keep in mind what now you will have to reinstall the web because <strong>fixcore.php</strong> now has new lines.</div>

>If you do not want to reinstall the web and manually enter this code then follow these steps:

**Enter to `application/config/fixcore.php`**

#### After line 20 - `$config['realmlist']` paste the following lines.

```php
/ *
| --------------------------------------------------------------------------
| Forum STAFF Color
| --------------------------------------------------------------------------
|
| Enter the code of the color you want for STAFF publications in the forum
| Use the following page to obtain the color code.
| http://htmlcolorcodes.com/
| Default: 00b4ff
|
* /
$config['staff_forum_color'] = "00b4ff";
```

{% include image.html url="/media/update1_001.jpg" width="100%" description="Example." %}



















