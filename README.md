# go-iso

The `go-iso` package is a Go library that provides ISO 3166-1 country codes and associated data. It allows you to retrieve country information by name, alpha-2 code, alpha-3 code, or numeric code.

## Features

- Comprehensive list of countries compliant with the ISO 3166-1 standard.
- Efficient lookup functions to retrieve country data based on different code formats.
- Easy integration into Go projects for internationalization and localization needs.

## Installation

To install the package, run:

```bash
go get github.com/yourusername/go-iso
```

## Usage

First, import the package into your Go project:

```go
import (
    "fmt"

    goiso "github.com/emil-petras/go-iso"
    "github.com/emil-petras/go-iso/types"
)
```

### Examples

#### Get Country by Name

```go
country := goiso.GetByName("Japan")
if country != nil {
    fmt.Printf("Country: %s, Alpha-2 Code: %s\n", country.Name, country.Alpha2)
} else {
    fmt.Println("Country not found")
}
```

#### Get Country by Alpha-2 Code

```go
country := goiso.GetByAlpha2("JP")
if country != nil {
    fmt.Printf("Country: %s, Numeric Code: %s\n", country.Name, country.Numeric)
} else {
    fmt.Println("Country not found")
}
```

#### Get Country by Alpha-3 Code

```go
country := goiso.GetByAlpha3("JPN")
if country != nil {
    fmt.Printf("Country: %s, Alpha-2 Code: %s\n", country.Name, country.Alpha2)
} else {
    fmt.Println("Country not found")
}
```

#### Get Country by Numeric Code

```go
country := goiso.GetByNumeric("392")
if country != nil {
    fmt.Printf("Country: %s, Alpha-3 Code: %s\n", country.Name, country.Alpha3)
} else {
    fmt.Println("Country not found")
}
```

## Data Structure

The `Country` type is defined in the `types` package and has the following structure:

```go
type Country struct {
    Name    string
    Alpha2  string
    Alpha3  string
    Numeric string
}
```

## Initialization

Upon package initialization, the country data is loaded into maps for efficient retrieval:

- `countryByName`
- `countryByAlpha2`
- `countryByAlpha3`
- `countryByNumeric`

This allows constant-time lookups when using the provided getter functions.

## Contributing

Contributions are welcome! Please follow these steps:

1. Fork the repository.
2. Create a new branch for your feature or bug fix.
3. Commit your changes with clear messages.
4. Submit a pull request.

## Disclaimer

This package aims to keep the country data up-to-date with the ISO 3166-1 standard. However, always verify the data for critical applications.

---

*For any issues or questions, please open an issue on the [GitHub repository](https://github.com/emil-petras/go-iso).*
```
