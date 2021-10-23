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

### noreturn

C++11

```text
[[noreturn]]$0
```

### carries_dependency

C++11

```text
[[carries_dependency]]$0
```

### deprecated

C++14

```text
[[deprecated(\"${1: description}\")]]$0
```

### maybe_unused

C++17

```text
[[maybe_unused]]$0
```

### nodiscard

C++17

```text
[[nodiscard${1:(\"${2: C++20 description}\")}]]$0
```

### fallthrough

C++17

```text
[[fallthrough]]$0
```

### no_unique_address

C++20

```text
[[no_unique_address]]$0
```

### likely

C++20

```text
[[likely]]$0
```

### unlikely

C++20

```text
[[unlikely]]$0
```

### concept

C++20

```text
template <class T>
concept ${1: concept_name} = requires (T& ${2:x}){
    $0
};
```

### static_assert

shortcut: `sta`

```text
static_assert(${1: expression}${2:, \"${3:description(C++17: optional)}\"});$0
```

### if constexpr

shortcut: `ifc`

```text
if constexpr(${1: expression}){
  $0
}
```

## Release Notes

### 0.0.1

The following snippet was added.

+ [`#if`](#if)
+ [`#elif`](#elif)
+ [`#ifdef`](#ifdef)
+ [`#ifndef`](#ifndef)
+ [`#include guards`](#include-guards)

### 0.0.2

The following snippet was added.

+ [`[[noreturn]]`](#noreturn)
+ [`[[carries_dependency]]`](#carries_dependency)
+ [`[[deprecated]]`](#deprecated)
+ [`[[maybe_unused]]`](#maybe_unused)
+ [`[[nodiscard]]`](#nodiscard)
+ [`[[fallthrough]]`](#fallthrough)
+ [`[[no_unique_address]]`](#no_unique_address)
+ [`[[likely]]`](#likely)
+ [`[[unlikely]]`](#unlikely)

### 0.0.3

The following snippet was added.

+ [`concept`](#concept)

### 0.0.4

The following snippet was added.

+ [`static_assert`](#static_assert)

### 0.0.5

The following snippet was added.

+ [`if constexpr`](#if-constexpr)
