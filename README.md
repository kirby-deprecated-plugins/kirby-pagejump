# Kirby Pagejump

*Require Kirby 2.3 Beta+*

**Version 0.1**

## Installation

Add `pagejump` folder into `/site/plugins/`.

## How it works

In a template or a snippet it's possible to use `$page->prev()` and `$page->next()`. When at the end of a collection you will be hit by the end wall.

Sometimes it can be good not be bound by the walls. When using `$page->jump($steps)` you can step any direction and always get a page.

It's similar to how an image slider or an ad rotator works.

## Usage

Echo the title of the previous page.

### Previous page

```php
$item = $page->jump(-1);
echo $item->title();
```

### Next page

Echo the title of the next page.

```php
$item = $page->jump(1);
echo $item->title();
```

### Jump multiple steps

Echo the title of the 5th page.

```php
$item = $page->jump(5);
echo $item->title();
```

## Example

A real example. Go to the next page or the previous one, without hitting the end "wall".

```php
<a href="<?php echo $page->jump(-1)->url(); ?>">
  <?php echo $page->jump(-1); ?>
</a>

<a href="<?php echo $page->jump(1)->url(); ?>">
  <?php echo $page->jump(1); ?>
</a>
```

To get an idea of how it works, look at the slider arrows on [getkirby.com](https://getkirby.com/). The arrows are not links but the result is similar, a page rotator.