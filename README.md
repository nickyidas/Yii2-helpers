Yii2 Helpers
============

Collection of useful helpers for Yii Framework 2.0

---

INSTALLATION
------------

Install from composer command:

```
$ php composer.phar require yidas/yii2-helpers
```

Or, in yii2 `composer.json`, manually require yidas/yii2-helpers.

```
"require": {
        ...
        "yidas/yii2-helpers": "*"
    },
```

---

HELPERS
-------

- **Navigation**  
  Web locator saving location and providing validation.

- **[Route](#route)**   
  Providing route information and validation.

- **RouteJS**  
  Redirector by JS base calling in Controller
  

---

DOCUMENTATION
-------------

### Route

#### Usage: (Supposing the current controller route is 'site/index')

```
Route::in('site');          // True for site/*
Route::is('site/index');    // True for site/index
Route::get();               // Get such as 'site/index'
Route::getByLevel(1);       // Get 'site' from 'site/index'

// Root Level usage for filtering prefix from route
Route::setRootLevel(1);     // Set the rootLevel to 1
Route::get();               // Get 'index' from 'site/index' 
Route::setRootLevel();      // Get the rootLevel back to 0
Route::get();               // Get 'site/index' from 'site/index'
```

#### Example in View:

```
<ul class="sidebar-menu">
  <li class="<?php if(Route::in('site')):?>active<?php endif ?> treeview">
    <a href="#">SITE控制器</a>
    <ul class="treeview-menu">
      <li class="<?php if(Route::is('site/index')):?>active<?php endif ?>"><a href="<?=Url::to(['site/index'])?>">列表</a></li>
      <li class="<?php if(Route::is('site/create')):?>active<?php endif ?>"><a href="<?=Url::to(['site/create'])?>">新增</a></li>
    </ul>
  </li>
</ul>
```
