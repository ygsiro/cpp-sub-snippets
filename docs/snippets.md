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

## user defined literal integral

shortcut: `udli`

```c++
${1:ReturnType} operator "" _${2:suffix}(unsigned long long ${3:count}){
  return ${1:ReturnType}();$0
}
```

## user defined literal float

shortcut: `udlf`

```c++
${1:ReturnType} operator "" _${2:suffix}(long double ${3:count}){
  return ${1:ReturnType}();$0
}
```

## user defined literal character

shortcut: `udlc`

```c++
${1:ReturnType} operator "" _${2:suffix}(${3|char,wchar_t,char16_t,char32_t|} ${4:str}){
  return ${1:ReturnType}();$0
}
```

## user defined literal string

shortcut: `udls`

```c++
${1:ReturnType} operator "" _${2:suffix}(${3|const char*,const wchar_t*,const char16_t*,const char32_t*|} ${4:str}, size_t ${5:N}){
  return ${1:ReturnType}();$0
}
```

## user defined literal raw

shortcut: `udlr`

```c++
${1:ReturnType} operator "" _${2:suffix}(const char* ${3:str}){
  return ${1:ReturnType}();$0
}
```

## user defined literal template

shortcut: `udlt`

```c++
template<char... ${1:S}>
${2:ReturnType} operator "" _${3:suffix}(){
  return ${2:ReturnType}();$0
}
```

## coroutine generator class

`#include <coroutine>`

```c++
class ${1:generator}{
public:
  struct promise_type;
  using handle = std::coroutine_handle<promise_type>;
  struct promise_type{
    ${3:T} ${4:current_value};
    static auto get_return_object_on_allocation_failure() { return ${1:generator}{nullptr}; }
    auto get_return_object() { return ${1:generator}{handle::from_promise(*this)}; }
    auto initial_suspend() { return std::suspend_always{}; }
    auto final_suspend() noexcept { return std::suspend_always{}; }
    void unhandled_exception() { std::terminate(); }
    void ${5|return_void,return_value|}() {$0}
    auto yield_value(${3:T} value){
      ${4:current_value} = value;
      return std::suspend_always{};
    }
  };

  ${1:generator}(${1:generator} const&) = delete;
  ${1:generator}(${1:generator}&& rhs)noexcept
    :${2:coro_}(rhs.${2:coro_}){rhs.${2:coro_} = nullptr;}
  ~${1:generator}(){if(${2:coro_}) ${2:coro_}.destroy();}
  bool move_next() { return ${2:coro_}? (${2:coro_}.resume(), !${2:coro_}.done()) : false; }
  ${3: T} ${4:current_value}(){return ${2:coro_}.promise().${4:current_value}; }
private:
  ${1:generator}(handle h):${2:coro_}(h){}
  handle ${2:coro_};
};
```

## attr11,14,17,20

```c++
//attr11
[[${1|noreturn,carries_dependency|}]]

//attr14
[[${1|noreturn,carries_dependency,deprecated("reason")|}]]

//attr17
[[${1|noreturn,carries_dependency,deprecated("reason"),maybe_unused,nodiscard,fallthrough|}]]

//attr20
[[${1|noreturn,carries_dependency,deprecated("reason"),maybe_unused,nodiscard("optional: reason"),fallthrough,no_unique_address,likely,unlikely|}]]
```
