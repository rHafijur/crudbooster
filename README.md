<h2>CRUDBOOSTER DEVELOPMENT</h2>
Do not use this master repository for production

<h3>Installation</h3>
Make sure you have installed newest laravel

<code>composer require crocodicstudio/crudbooster=dev-master</code>

Then don't forget to run the crudbooster installation command :
 
<code>php artisan crudbooster:install</code>

<h3>Quick Start</h3> 
Whatever you want to use laravel artisan serve or xampp . 
I assume you can go to the default crudbooster path 
<code>/developer/login</code>

Little different? yep. For the first time, you need to make your 
some modules, menus, and users for your new backend.

Developer Area : <br/>
default path : <code>/developer</code><br/>
default user : developer<br/>
default pass : developer<br/>

<strong>WARNING PLEASE DON'T FORGET TO CHANGE THE DEFAULT DEVELOPER CREDENTIAL AT 
<code>/config/crudbooster.php</code></strong>

1. Create your modules
1. Create your roles
1. Add new User

Now you can log out, and try the admin panel by visiting <code>/admin/login</code>

<quote>
You can always change the admin login at /config/crudbooster.php
</quote>

<h3>Basic Code Knowledge</h3>
In this new CRUDBooster, we use single scaffolding for index table and form. 
For example : 

```php
function cbInit() {
    $this->setTable("books");
    $this->setPageTitle("Book Data");
    
    $this->addText("Title");
}
```

As you can see we add column title it will show at index table, detail, add and edit form.

<h3>Types</h3>
These bellow are some types that you can use to make form input :
 
## Text
<strong>EXAMPLE</strong>

```php
    $this->addText("Foo Bar");
    $this->addText("Foo bar","foo_bar","field_foobar");
```

Parameters available : <br/>

| Name              | Description       |
| ----------------- | ----------------- |
| $label            | The input label (Required)   |
| $name             | The input name (Optional)    |
| $field_to_save    | The field name if not same with the name (Optional) |

Additional Options available : <br/>

| Method            | Description       |
| ------------------ | ---------------- |
| <code>->maxLength(100);</code> | Set max length limit
| <code>->minLength(5);</code> | Set min length limit |

Additional options example :
```php
    $this->addText("Foo Bar")->maxLength(100)->minLength(5);
```