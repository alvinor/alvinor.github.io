## @return

The @return tag is used to document the return value of functions or methods.

### Syntax
 
> @return [Type] [<description>]

### Description

With the @return tag it is possible to document the return type and function of a function or method. When provided it MUST contain a Type to indicate what is returned; the description on the other hand is OPTIONAL yet RECOMMENDED in case of complicated return structures, such as associative arrays.

The @return tag MAY have a multi-line description and does not need explicit delimiting.

It is RECOMMENDED when documenting to use this tag with every function and method. Exceptions to this recommendation are:

 + *constructors*, the @return tag MAY be omitted here, in which case @return self is implied.
 + *functions* and *methods* without a `return` value, the @return tag MAY be omitted here, in which case @return void is implied.

This tag MUST NOT occur more than once in a PHPDoc and is limited to Structural Elements of type method or function.

### Effects in phpDocumentor

Structural Elements of type method or function, that are tagged with the @return tag, will have an additional section Returns in their content description that shows the return Type and description.

If the return Type is a class that is documented by phpDocumentor, then a link to that class�� documentation is provided.

###Examples

Singular type:

```php
 /**
  * @return integer Indicates the number of items.
  */
 function count()
 {
     <...>
 }
```

Function can return either of two types:

```php
 /**
  * @return string|null The label's text or null if none provided.
  */
 function getLabel()
 {
     <...>
 }
```