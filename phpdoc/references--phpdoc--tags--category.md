## @category

<important>
Important This tag is considered deprecated and may be removed in a future version of phpDocumentor. It is recommended to use the @package tag��s ability to provide multiple levels.
</important>

The `@category` tag is used to organize groups of `packages` together.

### Syntax

> @category [description]

### Description

The @category tag was meant in the original de-facto Standard to group several Structural Elements their @package tags into one category. These categories could then be used to aid in the generation of API documentation.

This was necessary since the @package tag, as defined in the original Standard, did not contain more than one hierarchy level; since this has changed this tag SHOULD NOT be used.

Please see the documentation for @package for details of its usage.

This tag MUST NOT occur more than once in a DocBlock.

### Effects in phpDocumentor

The @category tag has no significant effect in phpDocumentor. It will be shown with the description information of associated Structural Elements and is inherited by classes and interfaces.

Examples

```php
 /**
  * Page-Level DocBlock
  *
  * @category MyCategory
  * @package  MyPackage
  */
```