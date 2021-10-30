# Snippets example

`$1`-`$9`: placeholders
`$0`: last position

## #if

```cpp
#if $1
$0
#endif // $1
```

## #elif

```cpp
#elif $1
```

## #else

```cpp
#else
```

## #define

```cpp
#define $1
```

## #ifdef

```cpp
#ifdef $1
$0
#endif // $1
```

## #ifndef

```cpp
#ifndef $1
$0
#endif // $1
```

## #include

shortcut: `#inc`

```cpp
#include 
```

## #include-guards

shortcut: `#hdr`

```cpp
#ifndef $1
#define $1
$0
#endif // $1
```

If the file name is `header.hpp`, the default value of `$1` is `HEADER_HPP`.

## has-include

```cpp
#if __has_include($1)
$0
#else
#endif
```

## noreturn

```cpp
//C++11
[[noreturn]]
```

## carries_dependency

```cpp
//C++11
[[carries_dependency]]
```

## deprecated

```cpp
//C++14
[[deprecated("$1")]]$0
```

## nodiscard

```cpp
//C++17
[[nodiscard$1]]$0
```

## maybe_unused

```cpp
//C++17
[[maybe_unused]]
```

## fallthrough

```cpp
//C++17
[[fallthrough]]
```

## no_unique_address

```cpp
//C++20
[[no_unique_address]]
```

## likely

```cpp
//C++20
[[likely]]
```

## unlikely

```cpp
//C++20
[[unlikely]]
```

## concept

```cpp
//C++20
template <class T>
concept $1 = requires (T& $2){
  $0
};
```

## static_assert

```cpp
//C++11.
static_assert($1, "$2");
```

## if-constexpr

```cpp
//C++17
if constexpr($1){
  $0
}
```

## alignas

```cpp
//C++11
alignas($1)
```

## alignof

```cpp
//C++11
alignof($1)
```

## using new name

```cpp
//C++11
using ${1:identifier} = ${2:type};$0
```

## template using new name

```cpp
//C++11
template<${1|class,typename|} ${2:T}>
using ${3:identifier} = ${4:type}<${2:T}>;$0
```
