# Benchmark Analysis of SearchValues<T>

## Overview

This documentation outlines the results from benchmarking tests conducted using the BenchmarkDotNet tool, a recognized standard for performance testing in the .NET community. Our focus was on evaluating the performance of different search methods applied to strings of varying lengths.

## Benchmark Design

The benchmark was structured to test three distinct search methods to determine their efficiency:

1. **IndexOfFirstAlphaNumericSimple**: Searches for the first alphanumeric character in the simple string "Owner.Name.Title".
2. **IndexOfFirstAlphaNumericLong**: Searches for the first alphanumeric character in a longer string consisting of 2062 characters.
3. **IndexOfSearchValuesLong**: Utilizes the SearchValues method for optimized search in the same long string as above.

## Benchmark Results

The following results demonstrate the performance of each method, captured on a system equipped with AMD Ryzen 7 6800H and Radeon Graphics, running Windows 11 with .NET SDK 8.0.202:

```ruby
BenchmarkDotNet v0.13.12, Windows 11
AMD Ryzen 7 6800H with Radeon Graphics
.NET SDK 8.0.202

| Method                          | Mean      | Error     | StdDev    | Allocated |
|---------------------------------|-----------|-----------|-----------|-----------|
| IndexOfFirstAlphaNumericSimple  | 4.715 ns  | 0.0328 ns | 0.0291 ns |         - |
| IndexOfFirstAlphaNumericLong    | 52.356 ns | 0.8546 ns | 0.7994 ns |         - |
| IndexOfSearchValuesLong         | 4.076 ns  | 0.0267 ns | 0.0236 ns |         - |
