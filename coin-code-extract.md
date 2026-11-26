# Coin / recharge code extract

Selected code excerpts read directly from `Star-Maker-1-source-java.zip`. Generated metadata and parcel boilerplate are omitted. This is decompiled client code, not a buildable Android project or app patch.

Recharge channel models distinguish Google Play and H5: `RechargeChannel.RECHARGE_TYPE_GOOGLE = 0`, `RECHARGE_TYPE_H5 = 1`, with `rechargeType`, `url`, `rechargeHalfScreenUrl`, and `rechargeHalfScreenScenes` fields.

Recharge dialog config includes `DIALOG_STYLE_FIRST_RECHARGE = 1`, `DIALOG_STYLE_ONLINE = 2`, `DIALOG_STYLE_NEW_FIRST_RECHARGE = 4`, and `DIALOG_STYLE_H5_RECHARGE = 5`, plus a `List<RechargeListItem>` containing coin/package counts and display fields.

The route map in `sources/defpackage/xdq.java` has these entries:

```java
new RouteItem("sm://particular/recharge", "com.ushowmedia.starmaker.pay.ParticularSkuPurchaseAct", "", "");
new RouteItem("sm://vip/recharge", "com.ushowmedia.starmaker.pay.NewRechargeActivity", "", "");
```

Those activity implementations were not present as Java files in the supplied source archive, so the actual recharge UI and purchase flow were not extracted here.

The purchase request/response models contain these fields:

```java
// GoogleOrderCheckBody
purchaseData; // @fur("purchase_data")
signature; // @fur("signature")
useServerConsume; // @fur("use_server_consume")

// GoogleOrderCheckResponse.DataBean
current_gold;
gold;
productId;
useClientConsume; // @fur("use_client_consume")

// PaytmOrderCheckBody
orderId; // @fur("order_id")
data;

// TrackPaymentBody
orderId;
data; // @fur("thp_status")
```

These fields show purchase-verification and coin-balance data are represented in the client models. They do not establish whether a balance can be granted locally or whether the server enforces it. The APK DEX files were searched for ASCII coin/recharge/payment/billing/purchase strings; matches occur across multiple DEX files in both supplied APK candidates. The four supplied Ghidra C files were searched for coin, coins, recharge, wallet, payment, purchase, billing, and SKU strings; none matched. Ghidra itself was not run in this pass.
