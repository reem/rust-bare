# Rust-Bare

> A barebones rust skeleton with Cargo

I use this to create new modules in a snap.

Just:

```bash
rust-create () {
    name=$1
    description=${2:-""}
    dir_name="rust-$1"

    # Get and clear the repo.
    git clone https://github.com/reem/rust-bare $dir_name && cd $dir_name
    rm -rf .git README.md

    # Insert name and description.
    sed -i '' "s/project-name/$name/g" Cargo.toml README.in.md src/lib.rs .travis.yml
    sed -i '' "s/project-description/$description/g" Cargo.toml README.in.md src/lib.rs

    # Move template files to final locations.
    mv README.in.md README.md

    # Go!
    git init
}
```

