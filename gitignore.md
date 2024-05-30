# Gitignore Guidelines

1. We prefer absolute paths.

    ```diff
    - build
    - .venv
    - Cargo.lock
    + /build
    + /.venv
    + /Cargo.lock
    ```

1. Paths that are expected to be directories should be prefixed with a `/`.

    ```diff
    @ gitignore.md
    - /build
    - /.venv
    + /build/
    + /.venv/
    ```

1. If the ignores are _only_ relevant to a specific project/folder, we prefer to
   put them in the `.gitignore` file of that project/folder. But try to keep it
   simple.

    ```diff
    @ gitignore.md
    - /packages/frontend/node_modules
    @ packages/frontend/.gitignore
    + node_modules
    ```

1. You can still be granular with enough generality on subdirectories.

    ```diff
    @ gitignore.md
    - /crates/my_pack/target/
    + /crates/*/target
    ```

1. Editor config can be tracked.

    ```diff
    @ gitignore.md
    - /.vscode/
    ```

    If you want to add a config to the workspace that should not be tracked in
    in VCS, you can use for example [multi-root workspaces].

1. Grouping should be like this:

    ```gitignore
    # Personal files / random stuff
    /tmp/           # Temporary/test/playground files
    *~              # Backup files

    # Our workflow
    /.direnv/       # Direnv, dev environment, and not everyone uses
    /result         # Nix build output
    /.venv/         # Python virtualenv

    # Generic language/tooling stuff
    /node_modules/  # Node modules 
    /target/        # Rust build output
    __pycache__/    # Python bytecode

    # Generic generic
    .DS_Store       # MacOS stuff
    ```

[multi-root workspaces]: https://code.visualstudio.com/docs/editor/multi-root-workspaces
