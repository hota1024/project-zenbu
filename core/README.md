# [WIP] RV32I core

## Development

### Requirements

| Package    | Version |
| :--------- | :------ |
| Veryl      | 0.14.0  |
| Verilator  | 5.036   |
| GNU Make   | 3.81    |
| LLVM Clang | 20.1.7  |

### Simulator

```
# Build .veryl files
make build
# Make simulator(verilator)
make sim
obj_dir/sim # ← Simulator file
```
