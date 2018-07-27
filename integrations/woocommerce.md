# WooCommerce

Official Repository

{% embed data="{\"url\":\"https://github.com/BTCPrivate/btcp-widget/blob/master/plugins/btcp-pay-woocommerce.php\",\"type\":\"link\",\"title\":\"BTCPrivate/btcp-widget\",\"description\":\"btcp-widget - JS widget for online shop payments\",\"icon\":{\"type\":\"icon\",\"url\":\"https://github.com/fluidicon.png\",\"aspectRatio\":0},\"thumbnail\":{\"type\":\"thumbnail\",\"url\":\"https://avatars0.githubusercontent.com/u/34813369?s=400&v=4\",\"width\":400,\"height\":400,\"aspectRatio\":1}}" %}

{% hint style="warning" %}
The plugin is still under heavy development. This guide will be updated make it easier to install in the future!

We are waiting for our plugin to get into the WordPress store!
{% endhint %}

## Downloading the plugin from GitHub

{% hint style="info" %}
You should have registered in [BTCP Pay](https://btcppay.com) before attemping to follow the steps.
{% endhint %}

Firstly, **download** the [WooCommerce plugin](https://github.com/BTCPrivate/btcp-widget/blob/master/plugins/btcp-pay-woocommerce.php) from the official repo by clicking on **'Raw'**.

![](../.gitbook/assets/btcp0.PNG)

Then **right click** and click on **'Save as...'.**

![](../.gitbook/assets/btcp1.PNG)

Then click on **'Save'.**

{% hint style="success" %}
You have now downloaded the BTCP Pay WooCommerce plugin!
{% endhint %}

## Uploading the plugin to WordPress

Next we will need to **upload** the plugin on WordPress.

{% hint style="warning" %}
You must have access to your website through FTP and should be confident in how to navigate directories.
{% endhint %}

{% hint style="info" %}
Use an FTP client such as [FileZilla](https://filezilla-project.org/) or [WinSCP](https://winscp.net/eng/download.php). In this guide we will be using FileZilla.
{% endhint %}

Firstly, login to your website and navigate to your WordPress home directory.

Next go to your plugin directory, this is normally `/wp-content/plugins/`

![](../.gitbook/assets/btcp2.PNG)

Drag the .PHP file to the directory to upload it.

![](../.gitbook/assets/btcp3.png)

{% hint style="success" %}
You have now uploaded the plugin to WordPress!
{% endhint %}

## Activate the plugin

{% hint style="warning" %}
You must access to you administrator account on WordPress in order to activate the plugin.
{% endhint %}

Firstly login to your target WordPress site and click on `Plugins`

![](../.gitbook/assets/btcp4%20%281%29.png)

Next, look for a plugin called `Bitcoin Private for WooCommerce` and click on `Acitavte`

![](../.gitbook/assets/btcp5.png)

Once you have clicked on activate the website will redirect you directly you the configuration page.

{% hint style="danger" %}
Create a BTCP Pay button now if you haven't already
{% endhint %}

{% page-ref page="../cloud-hosted-guide/create-a-btcp-pay-button.md" %}

## Configure the plugin

To configure the plugin simply paste **btcpWidget.data from your widget.** It should look something like this:

```javascript
btcpWidget.data = {
    "id"          : "btcp_widget",
    "buttonData"  : "buy_A1_6",
    "merchantid"  : "414",
    "walletid"    : "2",
    "amount"      : 0.001,
    "itemid"      : "0",
    "description" : "Pepperoni Pizza",
    "transactiondetails" :
      {
          "size"    : "12 inch",
          "crust"   : "stuffed",
          "pan"     : "thin base"
      }
```

{% hint style="info" %}
If you want to make BTCP your store-wide currency you can do so by adding the line `"currency":  "BTCP",`  to your `btcpWidget.data`
{% endhint %}

Finally, click on save

![](../.gitbook/assets/btcp6.png)

{% hint style="success" %}
Your plugin should now be working and BTCP Pay activated succesfully!
{% endhint %}

![](../.gitbook/assets/btcp7.png)





