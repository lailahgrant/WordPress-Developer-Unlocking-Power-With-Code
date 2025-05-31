# To Echo and Not To Echo
> Why do certain `functions` need `**echo**`?

```php
<?php
//function doubles the number passed in it
function doubleMe($x){
    echo $x *2;
}
doubleMe(4);

?>
```
- Functions that `return` values are flexible. Can use the value the function returns anywhere.
```php
function doubleMe($y){
    return $y * 2; //statements are kept in memory waiting to be echoed
}
doubleMe(2); // will not display anything even if the function is called.
echo doubleMe(4); //this will display 8

```
>

```php
<?php
//function doubles the number passed in it
function doubleMe($x){
    return $x *2;
}

function tripleMe($x){
    return $x *3;
}

echo tripleMe(doubleMe(5)); //this will return 30

?>
```


> To display the functions with `return`, use `echo`

## WordPress Functions
```php
the_title();
get_the_title();

the_ID();
get_the_id();

```

> GENERAL RULE IN WORDPRESS
> ### get_() - It won't `echo` anything but will `return` a value. You just use that value however you see fit.
>
> ### the_() - WP will handle `echoing` and `outputing` the function.

#### Official WordPress Resources to use to learn which `Functions` to use.
- [Codex by WordPress](https://codex.wordpress.org/)
- [Developer by WordPress](https://developer.wordpress.org/)








