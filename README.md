# k8s-quantity-parser
A simple parser for rust k8s_openapi::apimachinery::pkg::api::resource::Quantity

### Install

```
[dependencies]
k8s_quantity_parser = "0.0.1"
```

### Usage

```rust
use k8s_openapi::apimachinery::pkg::api::resource::Quantity;
use k8s_quantity_parser::QuantityParser;

// Parse memory values to bytes
let mib = Quantity("1Mi".into());
let ret: i64 = 1048576;
assert_eq!(mib.to_bytes().ok().flatten().unwrap(), ret);

// Parse cpu values to milli units of CPU.
let cpu = Quantity("4".into());
let ret: i64 = 4000;
assert_eq!(cpu.to_milli_cpus().ok().flatten().unwrap(), ret)

```