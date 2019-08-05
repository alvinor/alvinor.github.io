## @internal

The `@internal` tag is used to denote that associated Structural Elements are elements internal to this application or library. It may also be used inside a long description to insert a piece of text that is only applicable for the developers of this software.

### Syntax

<block>
@internal [description]
</block>

or inline:

<block>
{@internal [description]}}
</block>

The inline version of this tag may, contrary to other inline tags, contain text but also other inline tags. To increase readability and ease parsing should the tag be terminated with a double closing brace, instead of a single one.

### Description

The `@internal` tag can be used as counterpart of the `@api` tag, indicating that the associated Structural Elements are used purely for the internal workings of this piece of software.

An additional use of @internal is to add internal comments or additional description text inline to the Long Description. This may be done, for example, to withhold certain business-critical or confusing information when generating documentation from the source code of this piece of software.

<block>
It is NOT RECOMMENDED to store passwords or security sensitive information in your DocBlock. Not even with this tag.
</block>

### Effects in phpDocumentor

Structural Elements, or parts of the long description when the tag is used inline, tagged with the @internal tag will be filtered out when creating the HTML output unless the `--parseprivate` command line argument is used.

The Abstract Syntax Tree will still contain the internal information. Any consumer of this file is responsible for filtering the information.

### Examples

Mark the count function as being internal to this project:

Normal tag:

```php
 /**
  * @internal
  *
  * @return integer Indicates the number of items.
  */
 function count()
 {
     <...>
 }

```

Inline tag:

```php
 /**
  * Counts the number of Foo.
  *
  * {@internal Silently adds one extra Foo to compensate for lack of Foo }}
  *
  * @return integer Indicates the number of items.
  */
 function count()
 {
     <...>
 }
```