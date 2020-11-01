<img alt="Bartholomew" src="https://usefathom.com/assets/fathom-cat08.svg" height="100" />

**FathomAnalyticsClient**

An experiemental Swift client to allow you to track your iOS users using [Fathom Analytics](https://usefathom.com).

## Installation

### Swift Package Manager

The Swift Package Manager is a tool for automating the distribution of Swift code and is integrated into the swift compiler.

Once you have your Swift package set up, adding FathomAnalyticsClient as a dependency is as easy as adding it to the dependencies value of your Package.swift.

```swift
dependencies: [
    .package(url: "https://github.com/samtgarson/FathomAnalyticsClient.git", .upToNextMajor(from: "0.0.1"))
]
```

## Usage

### Quick Start

1. Import FathomAnalyticsClient and instantiate a new client instance with your Fathom config:
```swift
import FathomAnalyticsClient

let analytics = FathomAnalyticsClient(siteID: siteID, environment: environment)
```

2. Track a page view:
```swift
analytics.track(page: "account")
```

3. Track a goal:
```swift
analytics.track(goal: "MFTZ2U9V", value: 30)
```

### API

#### `FathomAnalyticsClient.init`

| Parameter | Required | Description |
|-|-|-|
| `siteID` | * | Your Fathom site ID (something like `ABCDEFGH`) |
| `environment` | * | A string to identify the environment you're reporting from (this is to replace the concept of "host" in a web browser) |
| `url` |  | Your custom URL setup in Fathom, if you have one (defaults to Fathom's global API URL) |
| `logger` |  | Provide a custom, [`swift-log`](https://github.com/apple/swift-log) compliant, logging backend (defaults to logging to `stdout`) |

#### `FathomAnalyticsClient#track`

To track a page:

| Parameter | Required | Description |
|-|-|-|
| `page` | * | An identifier for the current page (replacing the concept of "path" in a web browser) |

To track a goal:

| Parameter | Required | Description |
|-|-|-|
| `goal` | * | The code for your goal (something like `ABCD1E2F`) |
| `value` | | The value of the goal, in cents |


## Contribute

Bug reports and pull requests are welcome on GitHub at https://github.com/samtgarson/FathomAnalyticsClient. This project is intended to be a safe, welcoming space for collaboration, and contributors are expected to adhere to the [Contributor Covenant](http://contributor-covenant.org) code of conduct.

### License

The module is available as open source under the terms of the [MIT License](http://opensource.org/licenses/MIT).
