## project:run

<note>
Note The contents for this chapter is not complete yet. Why not help us and contribute it at https://github.com/phpDocumentor/phpDocumentor2/tree/develop/docs
</note>

### Description

### Usage

```shell
$ phpdoc -d|-f <PATH> -t <PATH> [parameters]
```

```shell
$ phpdoc run -d|-f <PATH> -t <PATH> [parameters]
```

```shell
$ phpdoc project:run -d|-f <PATH> -t <PATH> [parameters]
```

### Parameters

#### -t|每target[=§＃§]

The directory in which the generated documentation will be placed.

#### -f|每filename[=§＃§]

Provide a single file to parse.

This parameter can be used to tell phpDocumentor to interpret a single file. This may be a single relative or absolute path. When providing a relative path, please keep in mind that the path is relative to the current working directory.

Wildcards * and ? are not supported by this parameter.

This parameter may be used in conjunction with the `-d` parameter.

#### -d|每directory[=§＃§]

Provide a comma-separated list of source folders to parse.

This parameter can be used to tell phpDocumentor which folders need to be interpreted. This may be a single relative or absolute path; or a list of paths separated by commas. When providing a relative path, please keep in mind that the path is relative to the current working directory.

Wildcards * and ? are supported by this parameter, but please keep in mind to surround the parameter value with double quotes or your operating system might try to interpret them instead of phpDocumentor doing so.

This parameter may be used in conjunction with the -f parameter.

#### 每encoding

*Starting with 2.0.0a12,* Sets the encoding type of your source files.

Add this parameter if the encoding of your source files is not UTF-8. Charset detection is not available, because it would be inaccurate, so you must use this parameter instead.

#### -e|每extensions[=§＃§]

#### -i|每ignore[※＃§]

Provide a comma-separated list of paths to skip when parsing.

#### 每ignore-tags[=§＃§]

#### 每hidden

#### 每ignore-symlinks

Tells the parser not to follow symlinks.

#### -m|每markers[=§＃§]

Provide a comma-separated list of markers to parse.

#### 每title[=§＃§]

Specify a title for the documentation.

Title defaults to ※phpDocumentor§.

#### 每force

Ignore exceptions and continue parsing.

#### 每validate

#### 每visibility[=§＃§]

Provide a comma-separated list of visibility scopes to parse.

This parameter may be used to tell phpDocumentor to only parse public properties and methods, or public and protected.

#### 每defaultpackagename[=§＃§]

#### 每sourcecode

*Starting with 0.16.0,* Stores the sourcecode of each file with the structure.

When this parameter is provided the parser will add a compressed, base64-encoded version of the parsed file＊s source as child element of the <file> element. This information can then be picked up by the transformer to generate a syntax highlighted view of the file＊s source code and even have direct links to specific lines.

<block>
Currently the transformer will add a link to the given file＊s source next to the name of the file in the top. In the future we will add direct links from elements to the line in this source code file.
</block>