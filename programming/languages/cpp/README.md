# C++ Guidelines

## Learning Resources

- [The C++ Programming Language (4th Edition)](http://www.stroustrup.com/4th.html)

## Coding Style

### Naming Conventions

1. **Types** must be in `UpperCamelCase`.
   ```cpp
   class FileSystem { };
   struct User { };
   ```
2. **Variables** must be in `snake_case`.
   ```cpp
   int user_count;
   int balance;
   ```
   Member variables must have a `m_` prefix.
   ```cpp
   char* m_buffer;
   ```
3. **Functions** must be verbs written in `snake_case`.
   ```cpp
   int compute_total();
   void clear();
   ```
4. **Namespaces** must be written in `lowercase`.
   ```cpp
   namespace io { };
   namespace math { };
   ```

### File Names

1. **Headers**  
   Header files should be named with `snake_case` and use the `.hpp`
   extension for C++ headers, and `.h` for plain C headers.
   - `file_system.hpp`
   - `array_view.hpp`
   - `unused.hpp`

### Syntax

1. **Braces**  
    Each brace occupies its own line:
    ```cpp
    if (condition)
    {
        x++;
    }

    for (const auto& variable : iterable)
    {
        x++;
    }

    while (condition)
    {
        x++;
    }

    switch (something)
    {
    case Something:
        break;
    }

    void do_something()
    {
        x++;
    }

    class Class
    {
    public:
        int m_x;
    };

    // Extra braces inside a function also follow this convention
    void do_something()
    {
        {
            // Another Scope
            int x;
            x++;
        }
    }
    ```

    Namespaces are an exception to the above:

    ``` {.sourceCode .c++}
    namespace sophi {

    // Stuff inside the namespace block has the same indentation as
    // the block itself;
    x++;

    } /* sophi */
    ```

    The final `/* sophi */` comment is mandatory.

## Documentation

Use [doxygen](http://www.stack.nl/~dimitri/doxygen/) for generating documentation from annotated
source code.