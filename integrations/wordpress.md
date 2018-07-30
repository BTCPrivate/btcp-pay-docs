# Wordpress

Official Repository

{% embed data="{\"url\":\"https://github.com/BTCPrivate/btcp-widget/blob/master/plugins/btcp-pay-wordpress.php\",\"type\":\"link\",\"title\":\"BTCPrivate/btcp-widget\",\"description\":\"btcp-widget - JS widget for online shop payments\",\"icon\":{\"type\":\"icon\",\"url\":\"https://github.com/fluidicon.png\",\"aspectRatio\":0},\"thumbnail\":{\"type\":\"thumbnail\",\"url\":\"https://avatars0.githubusercontent.com/u/34813369?s=400&v=4\",\"width\":400,\"height\":400,\"aspectRatio\":1}}" %}

{% hint style="warning" %}
The plugin is still under heavy development. This guide will be updated make it easier to install in the future!
{% endhint %}

## Downloading the plugin from GitHub

{% hint style="info" %}
You should have registered in [BTCP Pay](https://btcppay.com) before attempting to follow the steps.
{% endhint %}

Firstly, **download** the [WordPress plugin](https://github.com/BTCPrivate/btcp-widget/blob/master/plugins/btcp-pay-wordpress.php) from the official repo by clicking on **'Raw'**.

![](../.gitbook/assets/btcp8.png)

Then **right click** and click on **'Save as...'.**

![](../.gitbook/assets/btcp9.png)

Then click on **'Save'.**

{% hint style="success" %}
You have now downloaded the BTCP Pay WordPress plugin!
{% endhint %}

## Uploading the plugin to WordPress

Next we will need to **upload** the plugin on WordPress.

{% hint style="warning" %}
You must have access to your website through FTP and should be confident in how to navigate directories.
{% endhint %}

{% hint style="info" %}
Use an FTP client such as [FileZilla](https://filezilla-project.org/) or [WinSCP](https://winscp.net/eng/download.php)
{% endhint %}

Firstly, login to your website and navigate to your WordPress home directory.

Next go to your plugin directory, this is normally `/wp-content/plugins/`

![](../.gitbook/assets/btcp2.PNG)

Drag the .PHP file to the directory to upload it.

![](../.gitbook/assets/btcp10.png)

You have now uploaded the plugin to WordPress!



{% hint style="success" %}
You have now uploaded the BTCP Pay WordPress plugin!
{% endhint %}

## Activate the plugin

{% hint style="warning" %}
You must access to you administrator account on WordPress in order to activate the plugin.
{% endhint %}

Firstly login to your target WordPress site and click on `Plugins`

![](../.gitbook/assets/btcp4%20%281%29.png)

Next, look for a plugin called `Bitcoin Private for WordPress` and click on `Acitavte`

![](../.gitbook/assets/imagen%20%283%29.png)

{% hint style="success" %}
You have now activated the BTCP Pay WordPress plugin.
{% endhint %}

## Configuring the plugin

{% hint style="danger" %}
Create a BTCP Pay button now if you haven't already
{% endhint %}

{% page-ref page="../cloud-hosted-guide/create-a-btcp-pay-button.md" %}

Once activated you will be directly taken to the configuation page.  Please paste the widget code from your account on the [btcppay.com](https://btcppay.com) site into the box, it should like something like this:

```javascript
<!-- BTCP Pay Widget // -->
<!-- Set parameters and actions //-->
<script id="btcp_widget_data">
  var btcpWidget = {};
  btcpWidget.data = {
    "id"          : "btcp_widget",
    "buttonData"  : "buy_A1_0",
    "merchantid"  : "414",
    "walletid"    : "2",
    "amount"      : 123.45,
    "itemid"      : "0",
    "description" : "Pepperoni Pizza",
    "transactiondetails" :
      {
          "size"    : "12 inch",
          "crust"   : "stuffed",
          "pan"     : "thin base"
      }
  };

  btcpWidget.onPaymentSuccess = function(data) {
    alert("Payment success! Data:\n\n" + JSON.stringify(data));
  };

  btcpWidget.onPaymentFail = function(data) {
    alert("Payment failed! Reason: " + data.reason);
  }
</script>

<!-- Load core functionality //-->
<script src="//btcppay.com/widget.js" id="btcp_widget"></script>'
```

Once entered, click on **Save Changes.**

![](../.gitbook/assets/imagen%20%284%29.png)

{% hint style="success" %}
You have now configured the BTCP Pay for WordPress plugin.
{% endhint %}

## Using the plugin

### Within wordpress

You can use shortcodes to activate the BTCP Pay screen:

*  Fixed value used in the code you pasted: **\[btcp\_pay\_widget\]**
* Attribute value use: **\[btcp\_pay\_widget amount="987.654"\]**

### **Within code**

You can use a PHP function to call the BTCP Pay screen.

{% hint style="danger" %}
**Do not use this method** unless you know how to.
{% endhint %}

* Fixed value use: **btcp\_pay\_widget\(\);**
* Function argument value use: **btcp\_pay\_widget\(987.654\);**

{% hint style="success" %}
You can now use te plugin pay with BTCP Pay
{% endhint %}

