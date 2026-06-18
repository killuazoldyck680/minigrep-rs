# minigrep

A command-line search tool built in Rust, inspired by the classic Unix `grep` utility. This project was developed while following **Chapter 12 of [The Rust Programming Language](https://doc.rust-lang.org/book/)** (also known as "The Book"), and serves as a practical application of core Rust concepts.

---

## Features

- Search for a string pattern within any text file
- Case-sensitive and case-insensitive search modes
- Environment variable support for toggling search behavior
- Clean error handling with meaningful messages
- Output written to `stdout`; errors written to `stderr`

---

## Built With

This project covers the following Rust concepts from The Book:

| Concept | Description |
|---|---|
| **Structs** | Grouping configuration data using a `Config` struct |
| **`impl` blocks** | Associated functions like `Config::build()` |
| **Error Handling** | Using `Result<T, E>`, `Box<dyn Error>`, and the `?` operator |
| **Closures** | Used with iterator methods for filtering lines |
| **Iterators** | Leveraging `Iterator` trait methods (`filter`, `map`, etc.) |
| **Modules** | Separating logic into `lib.rs` and `main.rs` |
| **Environment Variables** | `std::env::var()` for runtime configuration |
| **File I/O** | Reading file contents with `std::fs` |
| **`eprintln!` macro** | Writing error output to `stderr` |
| **Test-Driven Development** | Unit tests for core search logic |

---

## Getting Started

### Prerequisites

- [Rust](https://www.rust-lang.org/tools/install) (stable toolchain)
- Cargo (comes bundled with Rust)

### Installation

```bash
# Clone the repository
git clone https://github.com/killuazoldyck680/minigrep.git

# Navigate into the project directory
cd minigrep

# Build the project
cargo build --release
jj
```

---

## Usage

```bash
cargo run -- <query> <file_path>
```

### Example

```bash
cargo run -- to poem.txt
```

**Output:**

```
Are you nobody, too?
How dreary to be somebody!
```

### Case-Insensitive Search

Set the `IGNORE_CASE` environment variable to enable case-insensitive search:

```bash
# Linux / macOS
IGNORE_CASE=1 cargo run -- to poem.txt

# Windows (PowerShell)
$Env:IGNORE_CASE=1; cargo run -- to poem.txt
```

---

## Running Tests

```bash
cargo test
```

Tests are defined in `lib.rs` and cover both `search()` and `search_case_insensitive()` functions.

---

## What I Learned

This project was a major milestone in learning Rust. Key takeaways:

- How to **structure a real Rust project** by separating concerns between `main.rs` and `lib.rs`
- How **Rust's ownership model** works in practice when passing data through functions
- The power of **iterators and closures** as a clean alternative to explicit loops
- Writing **testable code** from the start by thinking in terms of pure functions
- Using **environment variables** for lightweight runtime configuration without a CLI flags library

---

## Resources

- [The Rust Programming Language — Chapter 12](https://doc.rust-lang.org/book/ch12-00-an-io-project.html)
- [Rust Standard Library Docs](https://doc.rust-lang.org/std/)
- [Cargo Book](https://doc.rust-lang.org/cargo/)

---

## License

This project is open source and available under the [MIT License](LICENSE).