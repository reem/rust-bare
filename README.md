# Rust-Bare

> A barebones rust skeleton with Cargo

I use this to create new modules in a snap.

Just:

```bash
# Get and clear the repo.
git clone https://github.com/reem/rust-bare rust-project && cd rust-project
rm -rf .git README.md

# Insert name and description.
sed -i '' "s/project-name/$name/g" Cargo.toml README.in.md
sed -i '' "s/project-description/$description/g" Cargo.toml README.in.md

# Move template files to final locations.
mv README.in.md README.md

# Go!
git init
```

I packaged this into a tiny bash script:

```bash
rust-create () {
    name=$1
    description=${2:-""}
    dir_name="rust-$1"

    # Get and clear the repo.
    git clone https://github.com/reem/rust-bare $dir_name && cd $dir_name
    rm -rf .git README.md

    # Insert name and description.
    sed -i '' "s/project-name/$name/g" Cargo.toml README.in.md
    sed -i '' "s/project-description/$description/g" Cargo.toml README.in.md

    # Move template files to final locations.
    mv README.in.md README.md

    # Go!
    git init
}
```

