# Coin / recharge code extract

Extracted verbatim from the supplied `Star-Maker-1-source-java.zip`. These are decompiled Java model, request, and response classes, not a buildable project or app patch. The recharge/purchase activity implementations referenced by the route map were not present in this source archive. Supplied Ghidra C files were searched for coin/payment keywords and had no matches; Ghidra was not run in this pass. This bundle does not establish server-side coin behavior or lifetime free coins.

## `sources/com/ushowmedia/starmaker/general/bean/RechargeChannel.java`

```java
package com.ushowmedia.starmaker.general.bean;

import android.os.Parcel;
import android.os.Parcelable;
import defpackage.fur;
import java.util.List;
import kotlin.Metadata;
import kotlin.jvm.internal.DefaultConstructorMarker;

/* compiled from: r8-map-id-45013ab888a439ed2937876cab8d1c62206c8fdca8c993c112c909913faad726 */
@Metadata(d1 = {"\u0000.\n\u0002\u0018\u0002\n\u0002\u0010\u0000\n\u0000\n\u0002\u0010\b\n\u0000\n\u0002\u0010\u000e\n\u0002\b\u0002\n\u0002\u0010 \n\u0002\b\u0011\n\u0002\u0010\u0002\n\u0000\n\u0002\u0018\u0002\n\u0002\b\u0003\b\u0007\u0018\u0000 \u001e2\u00020\u0001:\u0001\u001eB;\u0012\b\b\u0002\u0010\u0002\u001a\u00020\u0003\u0012\n\b\u0002\u0010\u0004\u001a\u0004\u0018\u00010\u0005\u0012\n\b\u0002\u0010\u0006\u001a\u0004\u0018\u00010\u0005\u0012\u0010\b\u0002\u0010\u0007\u001a\n\u0012\u0004\u0012\u00020\u0005\u0018\u00010\b\u00a2\u0006\u0004\b\t\u0010\nJ\u0012\u0010\u0016\u001a\u0004\u0018\u00010\u00052\b\u0010\u0017\u001a\u0004\u0018\u00010\u0005J\u0006\u0010\u0018\u001a\u00020\u0003J\u0016\u0010\u0019\u001a\u00020\u001a2\u0006\u0010\u001b\u001a\u00020\u001c2\u0006\u0010\u001d\u001a\u00020\u0003R\u001e\u0010\u0002\u001a\u00020\u00038\u0006@\u0006X\u0087\u000e\u00a2\u0006\u000e\n\u0000\u001a\u0004\b\u000b\u0010\f\"\u0004\b\r\u0010\u000eR \u0010\u0004\u001a\u0004\u0018\u00010\u00058\u0006@\u0006X\u0087\u000e\u00a2\u0006\u000e\n\u0000\u001a\u0004\b\u000f\u0010\u0010\"\u0004\b\u0011\u0010\u0012R\u0018\u0010\u0006\u001a\u0004\u0018\u00010\u00058\u0006X\u0087\u0004\u00a2\u0006\b\n\u0000\u001a\u0004\b\u0013\u0010\u0010R\u001e\u0010\u0007\u001a\n\u0012\u0004\u0012\u00020\u0005\u0018\u00010\b8\u0006X\u0087\u0004\u00a2\u0006\b\n\u0000\u001a\u0004\b\u0014\u0010\u0015\u00a8\u0006\u001f"}, d2 = {"Lcom/ushowmedia/starmaker/general/bean/RechargeChannel;", "Landroid/os/Parcelable;", "rechargeType", "", "url", "", "rechargeHalfScreenUrl", "rechargeHalfScreenScenes", "", "<init>", "(ILjava/lang/String;Ljava/lang/String;Ljava/util/List;)V", "getRechargeType", "()I", "setRechargeType", "(I)V", "getUrl", "()Ljava/lang/String;", "setUrl", "(Ljava/lang/String;)V", "getRechargeHalfScreenUrl", "getRechargeHalfScreenScenes", "()Ljava/util/List;", "checkHalfScreenScene", "scene", "describeContents", "writeToParcel", "", "dest", "Landroid/os/Parcel;", "flags", "Companion", "shared_general"}, k = 1, mv = {2, 3, 0}, xi = 48)
/* loaded from: classes.dex */
public final class RechargeChannel implements Parcelable {
    public static final int RECHARGE_TYPE_GOOGLE = 0;
    public static final int RECHARGE_TYPE_H5 = 1;

    @fur("half_url_scenes")
    private final List<String> rechargeHalfScreenScenes;

    @fur("half_url")
    private final String rechargeHalfScreenUrl;

    @fur("recharge_type")
    private int rechargeType;

    @fur("url")
    private String url;
    public static final Parcelable.Creator<RechargeChannel> CREATOR = new Creator();

    public /* synthetic */ RechargeChannel(int i, String str, String str2, List list, int i2, DefaultConstructorMarker defaultConstructorMarker) {
        this((i2 & 1) != 0 ? 0 : i, (i2 & 2) != 0 ? null : str, (i2 & 4) != 0 ? null : str2, (i2 & 8) != 0 ? null : list);
    }

    public final String checkHalfScreenScene(String scene) {
        List<String> list;
        if (scene == null || (list = this.rechargeHalfScreenScenes) == null || !list.contains(scene)) {
            return null;
        }
        return this.rechargeHalfScreenUrl;
    }

    @Override // android.os.Parcelable
    public final int describeContents() {
        return 0;
    }

    public final List<String> getRechargeHalfScreenScenes() {
        return this.rechargeHalfScreenScenes;
    }

    public final String getRechargeHalfScreenUrl() {
        return this.rechargeHalfScreenUrl;
    }

    public final int getRechargeType() {
        return this.rechargeType;
    }

    public final String getUrl() {
        return this.url;
    }

    public final void setRechargeType(int i) {
        this.rechargeType = i;
    }

    public final void setUrl(String str) {
        this.url = str;
    }

    @Override // android.os.Parcelable
    public final void writeToParcel(Parcel dest, int flags) {
        dest.getClass();
        dest.writeInt(this.rechargeType);
        dest.writeString(this.url);
        dest.writeString(this.rechargeHalfScreenUrl);
        dest.writeStringList(this.rechargeHalfScreenScenes);
    }

    /* compiled from: r8-map-id-45013ab888a439ed2937876cab8d1c62206c8fdca8c993c112c909913faad726 */
    @Metadata(k = 3, mv = {2, 3, 0}, xi = 48)
    public static final class Creator implements Parcelable.Creator<RechargeChannel> {
        /* JADX WARN: Can't rename method to resolve collision */
        @Override // android.os.Parcelable.Creator
        public final RechargeChannel createFromParcel(Parcel parcel) {
            parcel.getClass();
            return new RechargeChannel(parcel.readInt(), parcel.readString(), parcel.readString(), parcel.createStringArrayList());
        }

        /* JADX WARN: Can't rename method to resolve collision */
        @Override // android.os.Parcelable.Creator
        public final RechargeChannel[] newArray(int i) {
            return new RechargeChannel[i];
        }
    }

    public RechargeChannel(int i, String str, String str2, List<String> list) {
        this.rechargeType = i;
        this.url = str;
        this.rechargeHalfScreenUrl = str2;
        this.rechargeHalfScreenScenes = list;
    }

    public RechargeChannel() {
        this(0, null, null, null, 15, null);
    }
}
```

## `sources/com/ushowmedia/live/model/RechargeDialogConfig.java`

```java
package com.ushowmedia.live.model;

import android.os.Parcel;
import android.os.Parcelable;
import com.ushowmedia.livelib.bean.LiveLoggerConstants;
import com.ushowmedia.livelib.bean.LiveVerifiedDataBean;
import com.ushowmedia.starmaker.online.bean.ActionType;
import defpackage.fur;
import java.util.List;
import kotlin.Metadata;
import kotlin.jvm.internal.DefaultConstructorMarker;
import kotlin.text.b;

/* compiled from: r8-map-id-45013ab888a439ed2937876cab8d1c62206c8fdca8c993c112c909913faad726 */
@Metadata(d1 = {"\u0000:\n\u0002\u0018\u0002\n\u0002\u0010\u0000\n\u0000\n\u0002\u0010\b\n\u0000\n\u0002\u0010\u000e\n\u0002\b\b\n\u0002\u0010\u000b\n\u0002\b\u0007\n\u0002\u0010 \n\u0002\u0018\u0002\n\u0002\b\u0003\n\u0002\u0010\u0002\n\u0000\n\u0002\u0018\u0002\n\u0002\b\u0004\b\u0007\u0018\u0000  2\u00020\u0001:\u0002\u001f B\u00a7\u0001\u0012\b\b\u0002\u0010\u0002\u001a\u00020\u0003\u0012\n\b\u0002\u0010\u0004\u001a\u0004\u0018\u00010\u0005\u0012\n\b\u0002\u0010\u0006\u001a\u0004\u0018\u00010\u0005\u0012\n\b\u0002\u0010\u0007\u001a\u0004\u0018\u00010\u0005\u0012\n\b\u0002\u0010\b\u001a\u0004\u0018\u00010\u0005\u0012\n\b\u0002\u0010\t\u001a\u0004\u0018\u00010\u0005\u0012\n\b\u0002\u0010\n\u001a\u0004\u0018\u00010\u0005\u0012\b\b\u0002\u0010\u000b\u001a\u00020\u0003\u0012\b\b\u0002\u0010\f\u001a\u00020\u0003\u0012\b\b\u0002\u0010\r\u001a\u00020\u000e\u0012\n\b\u0002\u0010\u000f\u001a\u0004\u0018\u00010\u0005\u0012\n\b\u0002\u0010\u0010\u001a\u0004\u0018\u00010\u0005\u0012\n\b\u0002\u0010\u0011\u001a\u0004\u0018\u00010\u0005\u0012\n\b\u0002\u0010\u0012\u001a\u0004\u0018\u00010\u0005\u00a2\u0006\u0004\b\u0013\u0010\u0014J\u0006\u0010\u0018\u001a\u00020\u0005J\u0006\u0010\u0019\u001a\u00020\u0003J\u0016\u0010\u001a\u001a\u00020\u001b2\u0006\u0010\u001c\u001a\u00020\u001d2\u0006\u0010\u001e\u001a\u00020\u0003R\u0012\u0010\u0002\u001a\u00020\u00038\u0006@\u0006X\u0087\u000e\u00a2\u0006\u0002\n\u0000R\u0014\u0010\u0004\u001a\u0004\u0018\u00010\u00058\u0006@\u0006X\u0087\u000e\u00a2\u0006\u0002\n\u0000R\u0014\u0010\u0006\u001a\u0004\u0018\u00010\u00058\u0006@\u0006X\u0087\u000e\u00a2\u0006\u0002\n\u0000R\u0014\u0010\u0007\u001a\u0004\u0018\u00010\u00058\u0006@\u0006X\u0087\u000e\u00a2\u0006\u0002\n\u0000R\u0014\u0010\b\u001a\u0004\u0018\u00010\u00058\u0006@\u0006X\u0087\u000e\u00a2\u0006\u0002\n\u0000R\u0014\u0010\t\u001a\u0004\u0018\u00010\u00058\u0006@\u0006X\u0087\u000e\u00a6\u0002\n\u0000"}, d2 = {"Lcom/ushowmedia/live/model/RechargeDialogConfig;", "Landroid/os/Parcelable;", "dialogStyle", "", "title", "", "titleIcon", "pendantIcon", LiveVerifiedDataBean.TYPE_DESC, "buttonText", ActionType.ACTION_TYPE_DEEPLINK, "coolTime", "weeklyLimit", "immediatelyPop", "", "descArgs", "topImage", "titleImage", "bottomImage", "<init>", "(ILjava/lang/String;Ljava/lang/String;Ljava/lang/String;Ljava/lang/String;Ljava/lang/String;Ljava/lang/String;IIZLjava/lang/String;Ljava/lang/String;Ljava/lang/String;Ljava/lang/String;)V", "list", "", "Lcom/ushowmedia/live/model/RechargeDialogConfig$RechargeListItem;", "getDescFormat", "describeContents", "writeToParcel", "", "dest", "Landroid/os/Parcel;", "flags", "RechargeListItem", "Companion", "shared_stgift"}, k = 1, mv = {2, 3, 0}, xi = 48)
/* loaded from: classes8.dex */
public final class RechargeDialogConfig implements Parcelable {
    public static final String DESC_PLACE_HOLDER = "{num}";
    public static final int DIALOG_STYLE_BENEFIT = 3;
    public static final int DIALOG_STYLE_FIRST_RECHARGE = 1;
    public static final int DIALOG_STYLE_H5_RECHARGE = 5;
    public static final int DIALOG_STYLE_NEW_FIRST_RECHARGE = 4;
    public static final int DIALOG_STYLE_ONLINE = 2;
    public static final int SCENE_CHAT = 128;
    public static final int SCENE_GIFT = 8;
    public static final int SCENE_HOME = 32;
    public static final int SCENE_LIVE = 1;
    public static final int SCENE_MEDIA = 16;
    public static final int SCENE_MULTI_VOICE = 4;
    public static final int SCENE_NONE = 0;
    public static final int SCENE_PARTY = 2;
    public static final String TRIGGER_BOTTOM_BUTTON = "bottom_button";
    public static final String TRIGGER_GIFT_PANEL = "gift_panel";
    public static final String TRIGGER_HOME = "home";
    public static final String TRIGGER_SEND_MESSAGE = "send_message";
    public static final String TRIGGER_USER_BEHAVIOR = "user_behavior";
    public static final String TRIGGER_VIEW_TIME = "view_time";

    @fur("bottom_image")
    public String bottomImage;

    @fur("button_text")
    public String buttonText;

    @fur("cool_time")
    public int coolTime;

    @fur(ActionType.ACTION_TYPE_DEEPLINK)
    public String deeplink;

    @fur(LiveVerifiedDataBean.TYPE_DESC)
    public String desc;

    @fur("desc_args")
    public String descArgs;

    @fur("dialog_style")
    public int dialogStyle;

    @fur("immediately_pop")
    public boolean immediatelyPop;

    @fur("list")
    public List<RechargeListItem> list;

    @fur("pendant_icon")
    public String pendantIcon;

    @fur("title")
    public String title;

    @fur("title_icon")
    public String titleIcon;

    @fur("title_image")
    public String titleImage;

    @fur("top_image")
    public String topImage;

    @fur("weekly_limit")
    public int weeklyLimit;
    public static final Parcelable.Creator<RechargeDialogConfig> CREATOR = new Creator();

    public /* synthetic */ RechargeDialogConfig(int i, String str, String str2, String str3, String str4, String str5, String str6, int i2, int i3, boolean z, String str7, String str8, String str9, String str10, int i4, DefaultConstructorMarker defaultConstructorMarker) {
        this((i4 & 1) != 0 ? 0 : i, (i4 & 2) != 0 ? null : str, (i4 & 4) != 0 ? null : str2, (i4 & 8) != 0 ? null : str3, (i4 & 16) != 0 ? null : str4, (i4 & 32) != 0 ? null : str5, (i4 & 64) != 0 ? null : str6, (i4 & 128) != 0 ? 0 : i2, (i4 & 256) != 0 ? 0 : i3, (i4 & 512) == 0 ? z : false, (i4 & 1024) != 0 ? null : str7, (i4 & 2048) != 0 ? null : str8, (i4 & 4096) != 0 ? null : str9, (i4 & 8192) != 0 ? null : str10);
    }

    @Override // android.os.Parcelable
    public final int describeContents() {
        return 0;
    }

    public final String getDescFormat() {
        String str = this.desc;
        if (str == null) {
            return "";
        }
        String str2 = this.descArgs;
        return b.p(str, "{num}", str2 != null ? str2 : "", true);
    }

    @Override // android.os.Parcelable
    public final void writeToParcel(Parcel dest, int flags) {
        dest.getClass();
        dest.writeInt(this.dialogStyle);
        dest.writeString(this.title);
        dest.writeString(this.titleIcon);
        dest.writeString(this.pendantIcon);
        dest.writeString(this.desc);
        dest.writeString(this.buttonText);
        dest.writeString(this.deeplink);
        dest.writeInt(this.coolTime);
        dest.writeInt(this.weeklyLimit);
        dest.writeInt(this.immediatelyPop ? 1 : 0);
        dest.writeString(this.descArgs);
        dest.writeString(this.topImage);
        dest.writeString(this.titleImage);
        dest.writeString(this.bottomImage);
    }

    /* compiled from: r8-map-id-45013ab888a439ed2937876cab8d1c62206c8fdca8c993c112c909913faad726 */
    @Metadata(k = 3, mv = {2, 3, 0}, xi = 48)
    public static final class Creator implements Parcelable.Creator<RechargeDialogConfig> {
        /* JADX WARN: Can't rename method to resolve collision */
        @Override // android.os.Parcelable.Creator
        public final RechargeDialogConfig createFromParcel(Parcel parcel) {
            parcel.getClass();
            return new RechargeDialogConfig(parcel.readInt(), parcel.readString(), parcel.readString(), parcel.readString(), parcel.readString(), parcel.readString(), parcel.readString(), parcel.readInt(), parcel.readInt(), parcel.readInt() != 0, parcel.readString(), parcel.readString(), parcel.readString(), parcel.readString());
        }

        /* JADX WARN: Can't rename method to resolve collision */
        @Override // android.os.Parcelable.Creator
        public final RechargeDialogConfig[] newArray(int i) {
            return new RechargeDialogConfig[i];
        }
    }

    /* compiled from: r8-map-id-45013ab888a439ed2937876cab8d1c62206c8fdca8c993c112c909913faad726 */
    @Metadata(k = 3, mv = {2, 3, 0}, xi = 48)
    public static final class RechargeListItem {

        @fur("icon")
        public String icon;

        @fur("label_icon")
        public String labelIcon;

        @fur(LiveLoggerConstants.Params.NUM)
        public int num;

        @fur("num_format")
        public String numFormat;

        @fur("text_icon")
        public String textIcon;

        public /* synthetic */ RechargeListItem(String str, String str2, int i, String str3, String str4, int i2, DefaultConstructorMarker defaultConstructorMarker) {
            this((i2 & 1) != 0 ? null : str, (i2 & 2) != 0 ? null : str2, (i2 & 4) != 0 ? 0 : i, (i2 & 8) != 0 ? null : str3, (i2 & 16) != 0 ? null : str4);
        }

        public RechargeListItem(String str, String str2, int i, String str3, String str4) {
            this.icon = str;
            this.textIcon = str2;
            this.num = i;
            this.numFormat = str3;
            this.labelIcon = str4;
        }

        public RechargeListItem() {
            this(null, null, 0, null, null, 31, null);
        }
    }

    public RechargeDialogConfig(int i, String str, String str2, String str3, String str4, String str5, String str6, int i2, int i3, boolean z, String str7, String str8, String str9, String str10) {
        this.dialogStyle = i;
        this.title = str;
        this.titleIcon = str2;
        this.pendantIcon = str3;
        this.desc = str4;
        this.buttonText = str5;
        this.deeplink = str6;
        this.coolTime = i2;
        this.weeklyLimit = i3;
        this.immediatelyPop = z;
        this.descArgs = str7;
        this.topImage = str8;
        this.titleImage = str9;
        this.bottomImage = str10;
    }

    public RechargeDialogConfig() {
        this(0, null, null, null, null, null, null, 0, 0, false, null, null, null, null, 16383, null);
    }
}
```

## `sources/com/ushowmedia/starmaker/purchase/network/model/request/GoogleOrderCheckBody.java`

```java
package com.ushowmedia.starmaker.purchase.network.model.request;

import defpackage.fur;

/* compiled from: r8-map-id-45013ab888a439ed2937876cab8d1c62206c8fdca8c993c112c909913faad726 */
/* loaded from: classes9.dex */
public class GoogleOrderCheckBody {

    @fur("activity_name")
    public String activityName;

    @fur("activity_tag")
    public String activityTag;

    @fur("page_source")
    public String pageSource;

    @fur("purchase_data")
    public String purchaseData;

    @fur("signature")
    public String signature;

    @fur("use_server_consume")
    public boolean useServerConsume;
}
```

## `sources/com/ushowmedia/starmaker/purchase/network/model/response/GoogleOrderCheckResponse.java`

```java
package com.ushowmedia.starmaker.purchase.network.model.response;

import defpackage.fur;

/* compiled from: r8-map-id-45013ab888a439ed2937876cab8d1c62206c8fdca8c993c112c909913faad726 */
/* loaded from: classes9.dex */
public class GoogleOrderCheckResponse extends BaseResponse {
    private DataBean data;

    /* compiled from: r8-map-id-45013ab888a439ed2937876cab8d1c62206c8fdca8c993c112c909913faad726 */
    public static class DataBean {
        private int activity_status;
        private long current_gold;
        private long gold;
        private String productId;
        private int tp_status;

        @fur("use_client_consume")
        private boolean useClientConsume;

        public int getActivity_status() {
            return this.activity_status;
        }

        public long getCurrent_gold() {
            return this.current_gold;
        }

        public long getGold() {
            return this.gold;
        }

        public String getProductId() {
            return this.productId;
        }

        public int getTp_status() {
            return this.tp_status;
        }

        public boolean isUseClientConsume() {
            return this.useClientConsume;
        }

        public void setActivity_status(int i) {
            this.activity_status = i;
        }

        public void setCurrent_gold(long j) {
            this.current_gold = j;
        }

        public void setGold(long j) {
            this.gold = j;
        }

        public void setProductId(String str) {
            this.productId = str;
        }

        public void setTp_status(int i) {
            this.tp_status = i;
        }

        public void setUseClientConsume(boolean z) {
            this.useClientConsume = z;
        }
    }

    public DataBean getData() {
        return this.data;
    }

    public void setData(DataBean dataBean) {
        this.data = dataBean;
    }
}
```

## `sources/com/ushowmedia/starmaker/purchase/network/model/request/PaytmOrderCheckBody.java`

```java
package com.ushowmedia.starmaker.purchase.network.model.request;

import defpackage.fur;
import kotlin.Metadata;
import kotlin.jvm.internal.DefaultConstructorMarker;

/* compiled from: r8-map-id-45013ab888a439ed2937876cab8d1c62206c8fdca8c993c112c909913faad726 */
@Metadata(d1 = {"\u0000\u0012\n\u0002\u0018\u0002\n\u0002\u0010\u0000\n\u0000\n\u0002\u0010\t\n\u0002\b\b\b\u0007\u0018\u00002\u00020\u0001B\u001d\u0012\b\b\u0002\u0010\u0002\u001a\u00020\u0003\u0012\n\b\u0002\u0010\u0004\u001a\u0004\u0018\u00010\u0001\u00a2\u0006\u0004\b\u0005\u0010\u0006R\u0016\u0010\u0002\u001a\u00020\u00038\u0006X\u0087\u0004\u00a2\u0006\b\n\u0000\u001a\u0004\b\u0007\u0010\bR\u0018\u0010\u0004\u001a\u0004\u0018\u00010\u00018\u0006X\u0087\u0004\u00a2\u0006\b\n\u0000\u001a\u0004\b\t\u0010\n\u00a8\u0006\u000b"}, d2 = {"Lcom/ushowmedia/starmaker/purchase/network/model/request/PaytmOrderCheckBody;", "", "orderId", "", "data", "<init>", "(JLjava/lang/Object;)V", "getOrderId", "()J", "getData", "()Ljava/lang/Object;", "shared_purchase"}, k = 1, mv = {2, 3, 0}, xi = 48)
/* loaded from: classes9.dex */
public final class PaytmOrderCheckBody {

    @fur("data")
    private final Object data;

    @fur("order_id")
    private final long orderId;

    public /* synthetic */ PaytmOrderCheckBody(long j, Object obj, int i, DefaultConstructorMarker defaultConstructorMarker) {
        this((i & 1) != 0 ? 0L : j, (i & 2) != 0 ? null : obj);
    }

    public final Object getData() {
        return this.data;
    }

    public final long getOrderId() {
        return this.orderId;
    }

    public PaytmOrderCheckBody(long j, Object obj) {
        this.orderId = j;
        this.data = obj;
    }

    public PaytmOrderCheckBody() {
        this(0L, null, 3, null);
    }
}
```

## `sources/com/ushowmedia/starmaker/purchase/network/model/request/TrackPaymentBody.java`

```java
package com.ushowmedia.starmaker.purchase.network.model.request;

import defpackage.fur;
import kotlin.Metadata;

/* compiled from: r8-map-id-45013ab888a439ed2937876cab8d1c62206c8fdca8c993c112c909913faad726 */
@Metadata(d1 = {"\u0000\u0018\n\u0002\u0018\u0002\n\u0002\u0010\u0000\n\u0000\n\u0002\u0010\t\n\u0000\n\u0002\u0010\b\n\u0002\b\u0007\b\u0007\u0018\u00002\u00020\u0001B\u0017\u0012\u0006\u0010\u0002\u001a\u00020\u0003\u0012\u0006\u0010\u0004\u001a\u00020\u0005\u00a2\u0006\u0004\b\u0006\u0010\u0007R\u0016\u0010\u0002\u001a\u00020\u00038\u0006X\u0087\u0004\u00a2\u0006\b\n\u0000\u001a\u0004\b\b\u0010\tR\u0016\u0010\u0004\u001a\u00020\u00058\u0006X\u0087\u0004\u00a2\u0006\b\n\u0000\u001a\u0004\b\n\u0010\u000b\u00a8\u0006\f"}, d2 = {"Lcom/ushowmedia/starmaker/purchase/network/model/request/TrackPaymentBody;", "", "orderId", "", "data", "", "<init>", "(JI)V", "getOrderId", "()J", "getData", "()I", "shared_purchase"}, k = 1, mv = {2, 3, 0}, xi = 48)
/* loaded from: classes9.dex */
public final class TrackPaymentBody {

    @fur("thp_status")
    private final int data;

    @fur("order_id")
    private final long orderId;

    public TrackPaymentBody(long j, int i) {
        this.orderId = j;
        this.data = i;
    }

    public final int getData() {
        return this.data;
    }

    public final long getOrderId() {
        return this.orderId;
    }
}
```

## `sources/com/ushowmedia/starmaker/purchase/network/model/response/RecordPaymentResponse.java`

```java
package com.ushowmedia.starmaker.purchase.network.model.response;

/* compiled from: r8-map-id-45013ab888a439ed2937876cab8d1c62206c8fdca8c993c112c909913faad726 */
/* loaded from: classes9.dex */
public class RecordPaymentResponse extends BaseResponse {
    private DataBean data;

    /* compiled from: r8-map-id-45013ab888a439ed2937876cab8d1c62206c8fdca8c993c112c909913faad726 */
    public static class DataBean {
        private long order_id;

        public long getOrder_id() {
            return this.order_id;
        }

        public void setOrder_id(long j) {
            this.order_id = j;
        }
    }

    public DataBean getData() {
        return this.data;
    }

    public void setData(DataBean dataBean) {
        this.data = dataBean;
    }
}
```
