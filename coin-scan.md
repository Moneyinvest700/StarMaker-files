# Coin scan

## Scope
- Reviewed the supplied `StarMaker2-9.23.apk` and the five ZIP artifacts already present on the repository's `master` branch.
- APK SHA-256: `2e66d96962ba91fe304ec4ff58139d5c31d2ec72325ab1160bd0858e0aa28b95`.
- The Ghidra archive contains four decompiled native C files. The Java archive contains 20,265 decompiled `.java` files; it is extracted app/dependency code, not an original Android project.

## Findings
- A keyword scan for coin/currency, billing/payment, recharge/top-up, balance, and gift terms returned no matches in the four supplied Ghidra C files. This is a text scan of those decompilations, not a full native call-graph analysis or proof that native code has no related behavior.
- Coin, billing, and payment-related references are present in the decompiled Java sources and the APK's DEX strings. The manifest/resources also include Google Play Billing indicators.
- These client-side references do not establish that coin balances or purchase entitlements are controlled only by the app. The release artifacts contain no backend implementation, so server validation and lifetime-free coin behavior cannot be confirmed from them.
- The release ZIPs have no Gradle project/build configuration. They are not a directly buildable Android project.

## Outcome
No application code or payment flow was changed. No APK was built, signed, installed, or behavior-tested. This report records static scan evidence only; it does not claim that coins can be safely granted by a client-only change.