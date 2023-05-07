```rust
struct Person {
    name: &'static str,
    email: &'static str,
    language: &'static str,
    jobs: &'static str,
}

impl Person {
    const fn new(name: &'static str, email: &'static str, language: &'static str, jobs: &'static str) -> Self {
        Self {
            name,
            email,
            language,
            jobs,
        }
    }
}

struct PersonBuilder {}

impl PersonBuilder {
    const fn new() -> Self {
        Self {}
    }

    const fn build(&self) -> Person {
        Person::new("hihumikan", "a[at]qqey.net", "ja-jp", "jobless")
    }
}

const HIHUMIKAN: Person = PersonBuilder::new().build();
```
