# BreakInfinity.cs

A C# port of [break_infinity.js](https://github.com/Patashu/break_infinity.js) - a solution for incremental games which want to deal with very large numbers (bigger in magnitude than 1e308, up to as much as 1e(9e15)) and want to prioritize speed over accuracy.

## Installation

Add package from git URL `https://github.com/frostbun/BreakInfinity.git` or add `"com.razenpok.breakinfinity": "https://github.com/frostbun/BreakInfinity.git"` to `manifest.json`

## BigDouble

`BigDouble` is a `double` replacement for very large numbers.

### ToString() Formats

- Incremental

```csharp
new BigDouble(105.6).ToString() == "105.6"
new BigDouble(105203.6).ToString() == "105.2A"
new BigDouble(105203122.6).ToString() == "105.2B"
new BigDouble(105203122.6).ToString("I") == "105.2B"
new BigDouble(105203122.6).ToString("I0") == "105B"
new BigDouble(105203122.6).ToString("I2") == "105.20B"
```

- General

```csharp
new BigDouble(105203122911321275.6).ToString("G") == "1.05203122911321E+17"
new BigDouble(105203122911321275.6).ToString("G0") == "1.05203122911321E+17"
new BigDouble(105203122911321275.6).ToString("G1") == "1E+17"
new BigDouble(105203122911321275.6).ToString("G4") == "1.052E+17"
```

- Exponential

```csharp
new BigDouble(105203122911321275.6).ToString("E") == "1.052031E+017"
new BigDouble(105203122911321275.6).ToString("E0") == "1E+017"
new BigDouble(105203122911321275.6).ToString("E4") == "1.0520E+017"
```

- Fixed

```csharp
new BigDouble(105203122911321275.6).ToString("F") == "105203122911321000.00"
new BigDouble(105203122911321275.6).ToString("F0") == "105203122911321000"
new BigDouble(105203122911321275.6).ToString("F4") == "105203122911321000.0000"
```

# Credits

[Patashu](https://github.com/Patashu) - for amazing library and major effort in porting to C#