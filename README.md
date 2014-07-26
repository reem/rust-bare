# Rust-Bare

> A barebones rust skeleton with Cargo

I use this to create new modules in a snap.

Just:

```bash
git clone https://github.com/reem/rust-bare your-project && cd $_
rm -rf .git README.md && sed -i '' 's/package-name/your-project/g' Cargo.toml
git init
```

I packaged this into a tiny bash script:

```bash
rust-create () {
    name=$1
    dir_name="rust-$1"
    git clone https://github.com/reem/rust-bare $dir_name && cd $dir_name
    rm -rf .git README.md && sed -i '' "s/package-name/$name/g" Cargo.toml
    git init
}
```

