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

## #include-guards

shortcut: `#hdr`

```cpp
#ifndef $1
#define $1
$0
#endif // $1
```

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
alignof($1)
```
