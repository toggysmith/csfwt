# C++ Shorter Fixed Width Types (CSFWT)

This is a single header library that defines shorter versions of the C++ fixed-width types:

|Old|New|
|---|---|
|std::int8_t|i8|
|std::int16_t|i16|
|std::int32_t|i32|
|std::int64_t|i64|
|std::uint8_t|u8|
|std::uint16_t|u16|
|std::uint32_t|u32|
|std::uint64_t|u64|
|float|f32|
|double|f64|

These are more similar to Rust's types. This allows you to write code such as:

```cpp
i32 sum(std::vector<i32> numbers) {
    return std::accumulate(numbers.begin(), numbers.end(), 0);
}
```

There is also support for `f32` and `f64` in place of `float` and `double` respectively:

```cpp
f64 mean(std::vector<f64> const numbers) {
    if (numbers.empty()) {
        throw std::invalid_argument("Cannot calculate mean of empty list of numbers.");
    }

    f64 const sum{ std::accumulate(numbers.begin(), numbers.end(), 0.0) };
    f64 const mean{ sum / numbers.size() };

    return mean;
}
```

The only caveat is that `f32` and `f64` are minimums, not fixed-width types.

The primary motivation is that these typedefs are more concise and therefore you are more likely to use them.