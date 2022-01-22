# ⏳moment.swift
A lightweight Swift date library for parsing, validating, manipulating, and formatting dates based on [moment.js](https://github.com/moment/moment/moment). 

## Under the hood

The goal of this project is to help developers leverage the power of moment.js in their Swift applications. Moment.swift uses the [JavaScriptCore Framework](https://developer.apple.com/documentation/javascriptcore) to run moment.js from within Swift. Under the hood, moment.swift is simply a wrapper around the moment.js library. By sharing the same code base, moment.swift can benefit from years of testing and bug fixes and can be easily updated every time moment.js is updated.

## Usage 

Drag and drop [moment.swift](https://raw.githubusercontent.com/byolabisi/moment.swift/main/moment.swift/moment.swift/moment.swift) and [moment-with-locales.min.js](https://raw.githubusercontent.com/byolabisi/moment.swift/main/moment.swift/moment.swift/moment-with-locales.min.js) into your Xcode project and you're good to go.

###### Supported version 2.19.1

## Multiple locale support

Out of the box, moment.swift supports a total of 239 locales. See the moment.js website for a [list of all supported locales](https://momentjs.com#multiple-locale-support).

## Documentation

The [official moment.js documentation](https://momentjs.com/docs/) can be used with moment.swift. Just make sure to take into account the few [syntax variations](https://github.com/byolabisi/moment.swift#syntax-differences) between the JavaScript and Swift versions.

## Syntax differences

The syntax of moment.swift is almost identical to its JavaScript counterpart, thanks to the similarities between the two languages. Almost all methods have been implemented without affecting the syntax. Below is a list of syntax differences between the JavaScript and Swift versions. The [official documentation](https://momentjs.com/docs/) of moment.js can be used by taking into account the following variations:

#### Objects

The main difference is in the way objects are declared in Swift, `{ hour:15, minute:10 }` becomes `[ "hour":15, "minute":10 ]`: 

```Swift
let today = moment([ "hour":15, "minute":10 ])
```

#### null

The JavaScript `null` data type becomes `NSNull()`:

```Swift
let isBetween = moment("2016-10-30").isBetween("2016-10-30", "2016-12-30", NSNull(), "()")
```

#### Date() objects

Moment.swift supports the native Swift `Date()` object. When passing a `Date()` to moment.swift, it is automatically converted to its JavaScript counterpart and vice versa:

```Swift
let today = moment(Date())
let dateObj = today.toDate()
```

#### Functions

To use a Swift closure with moment.swift, declare it with the `@convention(block)` attribute:

```Swift
let closure: @convention(block) (String) -> String = { now in
    // Do something
}

moment().calendar(NSNull(), [
    "sameDay": closure
])
```

## Built with

* [moment.js](https://github.com/moment/moment) - Parse, validate, manipulate, and display dates in javascript.
* [Swift](https://developer.apple.com/swift/) - The powerful programming language that is also easy to learn.
* [JavaScriptCore Framework](https://developer.apple.com/documentation/javascriptcore) - Evaluate JavaScript programs from within your Swift app.


## Contributing

When contributing to this repository, please first discuss the change you wish to make via issue, email, or any other method with the owners of this repository before making a change.

Update the [README.md](https://github.com/byolabisi/moment.swift/blob/main/README.md) with details of changes to the library.

Update the [tests](https://github.com/byolabisi/moment.swift/blob/main/moment.swift/moment.swift/AppDelegate.swift) by demonstrating the changes to the library.

Build the project and test all the features before submitting your pull request.

## Authors

* **Olabisi Oduola** 

* A big thanks to [Iskren Ivov Chernev](https://github.com/ichernev) and all the moment.js contributors.

## License

This project is licensed under the MIT License - see the [LICENSE](https://github.com/byolabisi/moment.swift/blob/main/LICENSE) file for details.
