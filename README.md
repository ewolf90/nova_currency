<h1 style="border-bottom:0">Nova Currency Mod</h1>
  
![Version](https://img.shields.io/badge/Version-v1.0.0-brightgreen.svg "Version") [![Nova](https://img.shields.io/badge/Nova-v2.6.1-orange.svg "Laravel Version")](http://www.anodyne-productions.com/nova) [![PHP](https://img.shields.io/badge/PHP-v5.3.0-blue.svg "PHP Version")](https://www.php.net/)
  
The **Nova Currency Mod** was designed by [Emily Wolf](mailto:emily@wolfsims.org) for use on the [Nova 2](http://www.anodyne-productions.com/nova) system created by [Anodyne Productions](http://www.anodyne-productions.com). This mod calculates an in-game currency for players based on the number of mission posts made by a character. This mod is in early stages of development and the information is static (meaning there is no way to subtract or exchange currency in-game).<br>

[Report a Bug](https://github.com/ewolf90/nova_currency/issues/new) 

## Screenshot
![Currency Mod Screenshot](http://wolfsims.org/images/currency_mod.png "Currency Mod Screenshot")

## Getting Started
### Installation without personnel_character.php page
If you ***do not*** have a `personnel_index.php` file in `/application/views/_base_override/main/pages`, follow the steps below:

1. Downloading `personnel_index.php` file from this directory
2. Upload the file to your Nova's `/application/views/_base_override/main/pages` directory 

*This template file is the same format as the default view located in `/nova/modules/core/views/_base/main/pages`. If you have a different or custom `personnel_index.php` file, disregard the instructions above and follow the next step.*

### Installation with personnel_character.php page
If you have a `personnel_index.php` file in `/application/views/_base_override/main/pages`, follow the steps below:

1. Open and edit the `personnel_index.php` file in `/application/views/_base_override/main/pages`
2. Navigate to the line that begins the Stats section (Cmd + F for `<h4 class="page-subhead"><?php echo $label['stats'];?></h4>`)
3. Within the list statement (`<ul>`) below the Stats header label in Step 2, add the following code into the file:
```php
<?php if ($postcount > 0): ?>
  <?php $currency = $postcount * 2; ?>
  <li><strong><?php echo $currency;?></strong> Bars of Latinum</li>
<?php endif;?>
```

### Change Currency
This mod displays currency in Gold Pressed Latinum (GPL). If you want to change the currency, edit line 65 of the `personnel_index.php` file or change the <li> statement before inserting it into your file.
 
Example (in USD):
```php
<li><strong><?php echo $currency;?></strong> United States Dollars</li>
```
### Change Calculation
This mod displays currency at a rate of 2 Bars of Latinum per mission posts. If you want to change the calculation, edit line 64 of the `personnel_index.php` file or change the statement before inserting it into your file.
 
Example (4 units of currency per mission post):
```php
<?php $currency = $postcount * 4; ?>
```

## Support
If you need any help installing or customizing this skin, please join the [Anodyne Productions Discord](https://discord.gg/qwfZt38) and use room #xtras. Otherwise, direct message me on Discord (@Emily#6153) or [send me an email](mailto:emily@wolfsims.org).

## Credits
The Nova Currency Mod was designed by [Emily Wolf](mailto:emily@wolfsims.org) for the [Nova 2](http://www.anodyne-productions.com/nova) system created by [Anodyne Productions](http://www.anodyne-productions.com). Edits are permissible so long as the original credits remain intact.
