# LockupLinear

[Git Source](https://github.com/sablierhq/v2-core/blob/8bfc7785e498ccde9a6d39ad2fc8998d9077f979/docs/contracts/v2/reference/core)

Quasi-namespace for the structs used in the {SablierV2LockupLinear} contract.

## Structs

### CreateWithDurations

Struct that encapsulates the parameters of the {SablierV2LockupLinear-createWithDurations} function.

```solidity
struct CreateWithDurations {
    address sender;
    address recipient;
    uint128 totalAmount;
    IERC20 asset;
    bool cancelable;
    LockupLinear.Durations durations;
    Broker broker;
}
```

### CreateWithRange

Struct that encapsulates the parameters of the {SablierV2LockupLinear-createWithRange} function.

```solidity
struct CreateWithRange {
    address sender;
    address recipient;
    uint128 totalAmount;
    IERC20 asset;
    bool cancelable;
    Range range;
    Broker broker;
}
```

### Durations

Simple struct that encapsulates (i) the cliff duration and (ii) the total duration.

```solidity
struct Durations {
    uint40 cliff;
    uint40 total;
}
```

### Range

Range struct used as a field in the lockup linear stream.

```solidity
struct Range {
    uint40 start;
    uint40 cliff;
    uint40 end;
}
```

### Stream

Linear lockup stream struct.

_The fields are arranged like this to save gas via tight variable packing._

```solidity
struct Stream {
    Lockup.Amounts amounts;
    address sender;
    uint40 startTime;
    uint40 cliffTime;
    bool isCancelable;
    IERC20 asset;
    uint40 endTime;
    Lockup.Status status;
}
```