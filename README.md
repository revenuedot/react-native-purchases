<!-- revenuedot:readme:start -->
<p align="center"><a href="https://revenuedot.app"><picture>
  <source media="(prefers-color-scheme: dark)" srcset="https://raw.githubusercontent.com/revenuedot/revenuedot/main/brand/kit/wordmark/revenuedot-lockup-white.svg">
  <img alt="RevenueDot" src="https://raw.githubusercontent.com/revenuedot/revenuedot/main/brand/kit/wordmark/revenuedot-lockup-black.svg" height="40">
</picture></a></p>

# RevenueDot React Native SDK

This is RevenueDot's MIT fork of RevenueCat's `react-native-purchases`: the same classes and method names, pointed at a RevenueDot server ([RevenueDot Cloud](https://app.revenuedot.app/signup) at `https://api.revenuedot.app`, or one you host) with RevenueDot's response-signing key built in, and kept in sync with upstream.

[![License: MIT](https://img.shields.io/badge/license-MIT-blue)](LICENSE) [![npm](https://img.shields.io/npm/v/@revenuedot/react-native-purchases?label=npm)](https://www.npmjs.com/package/@revenuedot/react-native-purchases) [![Upstream](https://img.shields.io/badge/upstream-RevenueCat%2Freact--native--purchases_10.10.2-lightgrey)](https://github.com/RevenueCat/react-native-purchases)

## Install

npm aliases keep every `import ... from "react-native-purchases"` as it is:
```json
{
  "dependencies": {
    "react-native-purchases": "npm:@revenuedot/react-native-purchases@10.10.2",
    "react-native-purchases-ui": "npm:@revenuedot/react-native-purchases-ui@10.10.2"
  }
}
```
Then `npx pod-install` (bare React Native) or `npx expo prebuild` (Expo). The native side resolves to RevenueDot's `RevenueDotPurchasesHybridCommon` pod and `app.revenuedot.purchases:purchases-hybrid-common`.

## Configure

```ts
import { Platform } from "react-native";
import Purchases from "react-native-purchases";

// Self-hosted server only: RevenueDot Cloud (https://api.revenuedot.app) is the default.
await Purchases.setProxyURL("https://revenuedot.example.com");
Purchases.configure({ apiKey: Platform.OS === "ios" ? "appl_..." : "goog_..." });   // each app's public key from the RevenueDot dashboard
```

The fork already trusts RevenueDot's signing key, so no signature or verification setting is needed. Full guide: https://revenuedot.app/docs/sdks/react-native.

## What RevenueDot adds

- **Self-host for free, or use RevenueDot Cloud** free up to $10,000 a month of tracked revenue ([pricing](https://revenuedot.app/pricing)).
- **The same REST API and webhook payloads** as RevenueCat, so your backend and integrations keep working ([API reference](https://revenuedot.app/docs/api)).
- **Paywalls, experiments and the Customer Center** built in the RevenueDot dashboard and rendered by this SDK ([guides](https://revenuedot.app/docs/guides)).
- **A one-line migration:** point the stock SDK at RevenueDot with `setProxyURL`, or install this fork and drop the line ([migration guide](https://revenuedot.app/docs/migrate)).

## Use with your coding agent

Coding agents can read this repository's docs and code on demand, so they use the right package and imports:

- **Context7:** https://context7.com/revenuedot/react-native-purchases
- **DeepWiki:** https://deepwiki.com/revenuedot/react-native-purchases
- **GitMCP:** https://gitmcp.io/revenuedot/react-native-purchases

## Links

- **Docs for this SDK:** https://revenuedot.app/docs/sdks/react-native
- **Example app:** https://github.com/revenuedot/examples/tree/main/mobile/react-native-expo
- **Releases and changelog:** https://github.com/revenuedot/react-native-purchases/releases (tags `<upstream version>-revenuedot`; upstream's changes are in `CHANGELOG.md`)
- **RevenueDot server and dashboard:** https://github.com/revenuedot/revenuedot
- **Fork pipeline (what we change and how upstream is merged):** https://github.com/revenuedot/revenuedot/tree/main/scripts/forks

RevenueDot is not affiliated with RevenueCat, Inc. RevenueCat's copyright notice stays in `LICENSE`; RevenueDot's changes are MIT too.

---

## Upstream README (RevenueCat's, unchanged)
<!-- revenuedot:readme:end -->

<h3 align="center">😻 In-App Subscriptions Made Easy 😻</h3>

[![License](https://img.shields.io/cocoapods/l/RevenueCat.svg?style=flat)](http://cocoapods.org/pods/RevenueCat)

RevenueCat is a powerful, reliable, and free to use in-app purchase server with cross-platform support. Our open-source framework provides a backend and a wrapper around StoreKit, Google Play Billing and RevenueCat Web Billing to make implementing in-app purchases and subscriptions easy. 

Whether you are building a new app or already have millions of customers, you can use RevenueCat to:

  * Fetch products, make purchases, and check subscription status with our [native SDKs](https://docs.revenuecat.com/docs/installation). 
  * Host and [configure products](https://docs.revenuecat.com/docs/entitlements) remotely from our dashboard. 
  * Analyze the most important metrics for your app business [in one place](https://docs.revenuecat.com/docs/charts).
  * See customer transaction histories, chart lifetime value, and [grant promotional subscriptions](https://docs.revenuecat.com/docs/customers).
  * Get notified of real-time events through [webhooks](https://docs.revenuecat.com/docs/webhooks).
  * Send enriched purchase events to analytics and attribution tools with our easy integrations.

Sign up to [get started for free](https://app.revenuecat.com/signup).

## React Native Purchases

React Native Purchases is the client for the [RevenueCat](https://www.revenuecat.com/) subscription and purchase tracking system. It is an open source framework that provides a wrapper around StoreKit, Google Play Billing, RevenueCat Web Billing and the RevenueCat backend to make implementing in-app purchases in React Native easy.

## Migrating from React-Native Purchases v4 to v5
- See our [Migration guide](./v4_to_v5_migration_guide.md)

## RevenueCat SDK Features
|   | RevenueCat |
| --- | --- |
✅ | Server-side receipt validation
➡️ | [Webhooks](https://docs.revenuecat.com/docs/webhooks) - enhanced server-to-server communication with events for purchases, renewals, cancellations, and more   
🎯 | Subscription status tracking - know whether a user is subscribed whether they're on iOS, Android or web  
📊 | Analytics - automatic calculation of metrics like conversion, mrr, and churn  
📝 | [Online documentation](https://docs.revenuecat.com/docs) and [SDK reference](https://revenuecat.github.io/react-native-purchases-docs/) up to date  
🔀 | [Integrations](https://www.revenuecat.com/integrations) - over a dozen integrations to easily send purchase data where you need it  
💯 | Well maintained - [frequent releases](https://github.com/RevenueCat/purchases-ios/releases)  
📮 | Great support - [Help Center](https://revenuecat.zendesk.com) 

## Getting Started
For more detailed information, you can view our complete documentation at [docs.revenuecat.com](https://docs.revenuecat.com/docs).

Please follow the [Quickstart Guide](https://docs.revenuecat.com/docs/) for more information on how to install the SDK.

Or view our React Native sample app:
- [MagicWeather](examples/MagicWeather)

## Requirements

The minimum React Native version this SDK requires is `0.73.0`.
In Android, minimum Kotlin version is `1.8.0`.

## SDK Reference
Our full SDK reference [can be found here](https://revenuecat.github.io/react-native-purchases-docs/).

---

## Installation

Expo supports in-app payments and is compatible with `react-native-purchases`. To use the SDK, [create a new project](https://docs.expo.dev/get-started/create-a-project/) and set up a [development build](https://docs.expo.dev/get-started/set-up-your-environment/?mode=development-build). Development builds enable native code and provide a complete environment for testing purchases.

```
$ npx expo install react-native-purchases
```

In Expo Go, the SDK automatically runs in **Preview API Mode**, replacing native calls with JavaScript mocks so your app loads without errors. Real purchases, however, require a development build.

### Using development builds

To fully test in-app purchases, you’ll need to create a [custom development build](https://docs.expo.dev/develop/development-builds/introduction/) with EAS. This ensures that all native dependencies, including `react-native-purchases`, are properly included.
