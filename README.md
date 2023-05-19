# SystemdParser: A Light-Weight Crate for Parsing Systemd Configuration Files

SystemdParser is a light-weight Rust crate that simplifies the management of systemd configuration files in a type-safe and DRY (don't repeat yourself) fashion. With SystemdParser, you can easily parse .service, .socket, .target, and .mount files, without having to worry about parsing strings or unwrapping any Options.

## Features:

Type safe: the crate uses Rust's strong typing system to ensure that the code using the configuration values does not have to parse strings or unwrap Options. All values already have the correct type.

Layered configuration: SystemdParser allows you to load and merge multiple sources of configuration, including environment variables, TOML, YAML, JSON5, and anything with a serde Deserializer.

Easy-to-use macros: SystemdParser provides the #[derive(Config)] macro, which is similar to confique's implementation, making it easy to define the configuration struct. The crate will automatically recognize and parse the specific values based on their type, such as date, time, bool, and so on.

With SystemdParser, you can generate configuration templates that describe all available config values to your users without repeating yourself.

## Installation:

You can install SystemdParser by adding the following line to your Cargo.toml file:

```toml
systemd_parser = "0.1.0"
```

Usage:

To use SystemdParser, simply add the #[derive(Config)] macro to your struct definition, like this:

```rust
#[derive(Config)]
struct MyConfig {
    // ...
}
```

Then, you can load and parse the configuration values from the corresponding systemd configuration file, like this:

```rust
let config = MyConfig::parse("/etc/systemd/system/my-service.service")?;
```

## Contributing:

If you find any bugs or have any feature requests, please feel free to open an issue or submit a pull request on GitHub at https://github.com/<username>/systemd_parser.

## License:

SystemdParser is released under the MIT License. See the LICENSE file for details.