## Glossary

### DocComment

### DocComments

This is a special type of comment which starts with /**, ends with */ and may contain any number of lines in between. Every line should start with an asterisk, which is aligned with the first asterisk of the opening clause.

Single line example:

```php
 /** <...> */
Multiline example:
```

```php
 /**
  * <...>
  */
```

### DocBlock

### DocBlocks

This is a DocComment containing a single PHPDoc and represents the basic in-source representation.

Example:

```php
 /**
  * Returns the name of this object.
  *
  * @return string
  */
```

### AST

### Abstract Syntax Tree

### Abstract Syntax Tree (AST)

phpDocumentor generates a XML file between parsing your source code and generating the HTML output. This structure file (called structure.xml) contains the raw analyzed data of your project, also called: an Abstract Syntax Tree.

This same file is also used by phpDocumentor to do incremental parsing of your project by comparing the contents of this file with the content on disk.

It is thus recommended to keep your structure file and allow phpDocumentor to re-use the contained information.

#### PHPDoc

This is a section of documentation which provides information on several aspects of Structural Elements.

A PHPDoc is usually enveloped in a DocComment.

Example:

```php
  Returns the name of this object.

  @return string
```

Example enveloped in a DocComment:

```php
 /**
  * Returns the name of this object.
  *
  * @return string
  */
```

### Structural Element

### Structural Elements

This is a collection of Programming Constructs which SHOULD be preceded by a DocBlock. The collection contains the following constructs:

  - file
  - require(_once)
  - include(_once)
  - class
  - interface
  - trait
  - function (including methods)
  - property
  - constant

It is RECOMMENDED to precede Structural Elements with a DocBlock at its definition and not with each individual usage.

Example:

```php
 /** @var int This is a counter. */
 $int = 0;

 // there should be no docblock here
 $int++;
```

```php
 /**
  * This class acts as an example on where to position a DocBlock.
  */
 class Foo
 {
     /** @var string|null Should contain a description if available */
     protected $description = null;

     /**
      * This method sets a description.
      *
      * @param string $description A text with a maximum of 80 characters.
      *
      * @return void
      */
     public function setDescription($description)
     {
         // there should be no docblock here
         $this->description = $description;
     }
 }
 
```

Another example is to document the variable in a foreach explicitly; many IDEs use this information to help you with auto-completion:

```php
 /** @var \Sqlite3 $sqlite */
 foreach($connections as $sqlite) {
     // there should be no docblock here
     $sqlite->open('/my/database/path');
     <...>
 }
 ```
 
### Type

This is a generic name for anything that can be returned or provided as identity for a value.

It is recommended to read the chapter Definition of a ‘Type’ for a detailed description.

### FQSEN

### Fully Qualified Structural Element Name (FQSEN)

Each documentable element can be referenced using a unique name based on its local name and any containers it is in.

It is best demonstrated using an example:

`\My\Space\MyClass::myMethod()`

This FQSEN identifies the myMethod method that is contained in the MyClass class, which in turn is contained inside the My\Space namespace.

### Template

### Templates
<note>
Note Here a text must be added
</note>

### Transformation

### Transformations

<note>
Note Here a text must be added
</note>

### Summary

<note>
Note Here a text must be added
</note>

### Description
<note>
Note Here a text must be added
</note>

### Tag

### Tags
<note>
Note Here a text must be added
</note>

### Inline Tag

### Inline Tags
<note>
Note Here a text must be added
</note>

### Annotation

### Annotations
<note>
Note Here a text must be added
</note>

### Plugin

### Service Provider

A Service Provider is part of the Plugin system for phpDocumentor. Each plugin must have a Service Provider class that will bind the classes necessary for that plugin into the Dependency Injection Container or one of it services.

The Service Provider is a concept coming from Pimple, the dependency injection container powering phpDocumentor.