# Style Guidelines

- [.gitignore guidelines](gitignore.md)

## General

1. All files have a single trailing line feed.

    ```diff
    @ thing.md
    foo\n
    - bar<EOF>
    + bar\n<EOF>
    ```

2. No trailing whitespace.

    ```diff
    @ style.md
    fn foo() {
    -    let x = bar();·
    -····
    +    let x = bar();
    +
        println!("{} {}", x, x+1);
    }
    ```

## Dependencies

1. Dependency groups:

- std lib
- external libs
- sibling libs
- internal libs

TODO: Example.
