# cpp-sub-snippets README

C++ snippets list.

## Features

+ `$1`-`$9`: place folder
+ `$0`: last position

### \#if

```text
#if $1
$0
#endif //$1
```

### \#elif

```text
#elif $1
```

### \#ifdef

```text
#ifdef $1
$0
#endif //$1
```

### \#ifndef

```text
#ifndef $1
$0
#endif //$1
```

### \#include guards

shortcut: `#hdr`

The default value of `$1` is the filename converted to uppercase and the `.` converted to an `_`.

```text
#ifndef $1:FILENAME_EXP
#define $1:FILENAME_EXP
$0
#endif //$1:FILENAME_EXP
```

## Release Notes

### 0.0.1

The following snippet was added.

+ [`#if`](#if)
+ [`#elif`](#elif)
+ [`#ifdef`](#ifdef)
+ [`#ifndef`](#ifndef)
+ [`#include guards`](#include-guards)
