<!-- revenuedot:banner:start -->
> [!NOTE]
> **Fork of RevenueCat's MIT SDK, maintained by RevenueDot, not affiliated with RevenueCat.** It keeps the upstream public API (`Purchases.configure`, `Purchases.shared`, every class and method name), so app code and RevenueCat's guides work unchanged. It talks to [RevenueDot](https://github.com/revenuedot/revenuedot) at `https://api.revenuedot.app` by default (`setProxyURL` still points it at a self-hosted server) and verifies RevenueDot's response signatures. RevenueCat's copyright notice is kept in `LICENSE`. Patches: [scripts/forks](https://github.com/revenuedot/revenuedot/tree/main/scripts/forks). **Status: pre-alpha, not yet published to package registries.**
>
> **Install:** `"react-native-purchases-ui": "npm:@revenuedot/react-native-purchases-ui@<version>"` next to the `react-native-purchases` alias.
>
> The upstream README follows, unchanged. Where it says RevenueCat's dashboard or API, use RevenueDot's.
<!-- revenuedot:banner:end -->

# React Native Purchases Store Galaxy

Galaxy Store add-on for `react-native-purchases`.

```ts
import Purchases from "react-native-purchases";
import { GALAXY_BILLING_MODE } from "react-native-purchases-store-galaxy";

Purchases.configure({
  apiKey: "galx_XYZ",
  store: "GALAXY",
  galaxyBillingMode: GALAXY_BILLING_MODE.TEST,
});
```
