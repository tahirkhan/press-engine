Press Engine
============

What is it?
--------------------------------------

A simple yet powerful templating engine in PHP for the times when you don't need bloated frameworks.

Getting Started
--------------------------------------

Installation
--------------------------------------

- [Download](https://github.com/tahirkhan/press-engine/archive/master.zip) and extract press-engine.php
- Drop it in your common require folder or in your project folder

Hello World
--------------------------------------

Follow these simple steps to run a hello world example

1. Create a template file greetings.tpl.php

```php
Greetings <?php echo $this->name ?>
```

2. Create your php application which will use a template. Lets call it helloworld.php

```php
<?php
require_once('press-engine.php');

$engine = new PressEngine('greetings.tpl.php',array('name'=>'Jay Z'));

echo $engine->contentString;
?>
```

3. Run your php application 

```bash
php helloworld.php
```

It should produce the following output:

```bash
Greetings Jay Z'
```

Including Templates within Templates
--------------------------------------


Sandwiching Templates
--------------------------------------

