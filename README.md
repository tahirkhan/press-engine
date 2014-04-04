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

#### Step 1. Create a template file greetings.tpl.php

```php
Greetings <?php echo $this->name ?>
```

#### Step 2. Create your php application which will use a template. Lets call it helloworld.php

```php
<?php
require_once('press-engine.php');
$engine = new PressEngine('greetings.tpl.php',array('name'=>'Jay Z'));
echo $engine->contentString;
?>
```

#### Step 3. Run your php application 

```bash
php helloworld.php
```

#### It should produce the following output:

```bash
Greetings Jay Z
```

Sandwiching Templates
--------------------------------------
Sandwiching Templates is useful when you want a template to include a container like a shell. 
To sandwich you can use startSuperTemplate(String template_path) method and endSuperTemplate() to mark the end.

#### Step 4. Create a template file body.tpl.php

```php
<html>
	<head>
		
	</head>
	<body>
		<?php echo $this->insertSubTemplateContent();?>
	</body>
</html>
```

#### Step 5. Modify greetings.tpl.php

```php
<?php $this->startSuperTemplate('body.tpl.php') ?>
Greetings <?php echo $this->name ?>
<?php $this->endSuperTemplate() ?>
```

#### Step 6. Run your php application 

```bash
php helloworld.php
```

#### It should produce the following output:

```bash
<html>
	<head>
		
	</head>
	<body>
		Greetings Jay Z
	</body>
</html>
```

Including Templates within Templates
--------------------------------------

To include templates you can use renderTemplate(String template_path) method.

#### Step 7. Create a template file title.tpl.php

```php
<title>Hello World Example</title>
```

#### Step 5. Modify body.tpl.php

```php
<html>
	<head>
		<?php echo $this->renderTemplate('title.tpl.php'); ?>
	</head>
	<body>
		<?php echo $this->insertSubTemplateContent();?>
	</body>
</html>
```

#### Step 6. Run your php application 

```bash
php helloworld.php
```

#### It should produce the following output:

```bash
<html>
	<head>
		<title>Hello World Example</title>
	</head>
	<body>
		Greetings Jay Z
	</body>
</html>
```
