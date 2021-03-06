#  ViruSafe for iOS

ViruSafe aims to help the fight with COVID-19 by offering people to share their symptoms as well track the spread of COVID-19 with an interactive map, that shows how the infection has spread throughout Bulgaria.

The ViruSafe mobile app provides access to the following:
- Receiving up-to-date information regarding COVID-19
- Regular sharing of symptoms
- Sharing your location, in order to compare your location to all users who have developed symptoms
- Option to be warned if you have been in close proximity to other symptomatic users
- Option to receive location-based notifications and alerts

<a href="https://apps.apple.com/bg/app/virusafe/id1506362170?mt=8"><img alt='Download on the App Store' src='https://linkmaker.itunes.apple.com/en-gb/badge-lrg.svg?releaseDate=2020-04-06&kind=iossoftware&bubble=ios_apps'/></a>

Overview:
- [ViruSafe for iOS](#virusafe-for-ios)
  - [Build Instructions](#build-instructions)
    - [Prerequisites](#prerequisites)
    - [Pods](#pods)
    - [Firebase](#firebase)
    - [Flex](#flex)
    - [Build Settings](#build-settings)
    - [Provisioning](#provisioning)
    - [Debug](#debug)
    - [Archive](#archive)
  - [Code Styleguide](#code-styleguide)
  - [Using the REST API](#using-the-rest-api)
    - [Using a Mock API](#using-a-mock-api)
  - [Contributing](#contributing)
  - [Security](#security)
  - [License](#license)

##  Build Instructions

### Prerequisites

- Mac computer
- Xcode
- Developer account
- iTunes Connect account (Optional)
- Clone the repository
- [Cocoapods dependency manager](https://cocoapods.org/)
- [Cocoapods Keys environment and application key store](https://github.com/orta/cocoapods-keys)

### Pods

- Navigate to the folder containing the Podfile in your Terminal app.
- Now install the pod (and any other necessary project dependencies) by executing the command: `pod install`.
- Open *COVID-19.xcworkspace* and build.

> **NB! After every change in `NetworkKit` you have to execute `pod install` and clean build your project.**

> **NB!  Cocoapods Keys in the Podfile is commented out so that you are not forced to add keys.**

### Firebase

In order to have working app you should add `GoogleService-Info.plist` to the project. You have to setup your own firebase project. You can have either one configuration for all targets or many (one per target). You can setup your own remote config. Check `RemoteConfigDefaults` for used keys.

### Flex

As you don't have Flex API key this build step will fail, but you're covered. We ship our code with default localization.

### Build Settings

Base SDK:  13.2 (latest)
Deployment Target:  10.0

> **NB! You can build an application with Base SDK 13.2 that runs under iOS 10. But then you have to take care to not use any function or method that is not available on iOS 10. If you do, your application will crash on iOS 10 as soon as this function is used.**

### Provisioning

Debug version is signed automatically. Release version uses manual signing. Both however are not opened, so you have to use your own signing, while testing.

### Debug

Bluetooth functionality can not be tested in the Simulator. *(Don't worry BT is not added yet)*

### Archive

- Select Generic iOS Device for building.
- Build the project using `Project -> Archive`.

## Code Styleguide

We decided to refer to [The Official raywenderlich.com Swift Style Guide](https://github.com/raywenderlich/swift-style-guide)

Contributors are expected to read through and familiarize themselves with the style guide as we're going to enforce it adding `swiftlint`.

## Using the REST API

Swagger Documentation for the ViruSafe REST API is available at the [ViruSafe SwaggerHub](https://app.swaggerhub.com/apis-docs/ViruSafe/viru-safe_backend_rest_api/1.0.0).

Also, the ViruSafe Swagger API Docs are available for [download as JSON](https://api.swaggerhub.com/apis/ViruSafe/viru-safe_backend_rest_api/1.0.0) and [as YAML](https://api.swaggerhub.com/apis/ViruSafe/viru-safe_backend_rest_api/1.0.0/swagger.yaml) files. These become useful when setting up your Mock API.

### Using a Mock API

To develop the mobile app against a Mock API, please check the guidelines on how to [Use a Mock API](USING-MOCK-API.md)

## Contributing

Read our [Contributing Guide](CONTRIBUTING.md) to learn about reporting issues, contributing code, and more ways to contribute.

## Security

If you happen to find a security vulnerability, we would appreciate you letting us know by contacting us on - virusafe.support (at) scalefocus.com and allowing us to respond before disclosing the issue publicly.

## License

Copyright 2020 SCALE FOCUS AD

Licensed under the Apache License, Version 2.0 (the "License");
you may not use this file except in compliance with the License.
You may obtain a copy of the License at

http://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing, software
distributed under the License is distributed on an "AS IS" BASIS,
WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
See the License for the specific language governing permissions and
limitations under the License.
