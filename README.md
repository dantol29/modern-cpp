# Transitioning from C++98

<details>
<summary><h1>C++11</h1></summary>

<details>
<summary><h2>Language Features</h2></summary>

### 1. Auto Keyword: Automatic type deduction.
```
auto x = 5;  // x is int
```
### 2. Range-Based For Loop: Simplified iteration over collections.
```
int arr[] = {1, 2, 3, 4, 5};

for (int value : arr)
    std::cout << value;
```
### 3. Lambda Expressions: Anonymous function objects.

**Syntax:** `[capture](parameters) -> return_type { body }`

- By Value [=]: Captures all variables used in the lambda by value.
- By Reference [&]: Captures all variables used in the lambda by reference.

```
int count = 0;
std::for_each(numbers.begin(), numbers.end(), [&count](int n) {
    count += n;
});
```
### 4. Static Assertions: Compile-time assertions.
It allows you to verify certain conditions during compilation rather than waiting for runtime execution.
```
static_assert(sizeof(int) == 4, "Integer size must be 4 bytes");
```
### 5. Rvalue References and Move Semantics: For efficient resource management.
Steal the resources from the source object, leaving it in a valid but empty state.
```
// Move constructor
ResourceHolder(ResourceHolder&& other) noexcept : data(other.data) {
    other.data = nullptr;  // Move ownership, source becomes empty
}

ResourceHolder res1(100); // Allocate memory for res1
ResourceHolder res2(std::move(res1)); // Move ownership to res2, res1 becomes empty
```
### 7. Uniform Initialization: Consistent syntax for initializing variables.
```
std::vector<int> data = {1, 4, 9};
```
### 8. Default and Deleted Functions: Specify default or disallowed special member functions.
A mechanism for explicitly controlling the compiler's generation of special member functions.

These are also known as the `Big Five` (Destructor, Default constructor, Copy constructor, Copy assignment operator, Move constructor, Move assignment operator)
```
class ResourceHolder {
public:
  // Use default compiler generated constructor
  ResourceHolder() = default;

  // Delete copy constructor and copy assignment operator
  ResourceHolder(const ResourceHolder&) = delete;
  ResourceHolder& operator=(const ResourceHolder&) = delete;
};

```
### 9. Override and Final Specifiers: Enhancements for virtual functions.
```
```
### 10. New String Literals: Raw string literals for multi-line strings.
```
```
</details>

<details>
<summary><h2>Library Features</h2></summary>

### 1. Smart Pointers: std::unique_ptr, std::shared_ptr, and std::weak_ptr.
```
```
### 2. Threading Library: std::thread, std::mutex, std::lock_guard, etc.
```
```
### 3. New Algorithms: Additions to the standard algorithms.
```
```
### 4. Chrono Library: Facilities for timekeeping and time point manipulation.
```
```
### 5. Regular Expressions: Regex library for pattern matching.
```
```
### 6. Initializer Lists: std::initializer_list for passing initializer lists to constructors.
```
```
</details>
</details>
