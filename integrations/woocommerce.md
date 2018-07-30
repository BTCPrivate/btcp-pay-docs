# WooCommerce

Official Repository

{% embed data="{\"url\":\"https://github.com/BTCPrivate/btcp-widget/blob/master/plugins/btcp-pay-woocommerce.php\",\"type\":\"link\",\"title\":\"BTCPrivate/btcp-widget\",\"description\":\"btcp-widget - JS widget for online shop payments\",\"icon\":{\"type\":\"icon\",\"url\":\"https://github.com/fluidicon.png\",\"aspectRatio\":0},\"thumbnail\":{\"type\":\"thumbnail\",\"url\":\"https://avatars0.githubusercontent.com/u/34813369?s=400&v=4\",\"width\":400,\"height\":400,\"aspectRatio\":1}}" %}

## Install form the WordPress plugin store

### Install & activate the plugin

Firstly login to your target WordPress site and click on `Plugins`

![](../.gitbook/assets/btcp4%20%281%29.png)

Next, click on `Add New`

![](../.gitbook/assets/imagen%20%285%29.png)

Now, on the search bar type `btcp-pay-woocommerce`

![](../.gitbook/assets/imagen.png)

And click on `Install Now`

![](../.gitbook/assets/imagen%20%282%29.png)

Wait until you get a message that says `Activate` and then click on it.

![](../.gitbook/assets/imagen%20%281%29.png)

{% hint style="success" %}
You have now activated the BTCP Pay for WooCommerce plugin!
{% endhint %}

### Configure the plugin

{% hint style="danger" %}
Create a BTCP Pay button now if you haven't already
{% endhint %}

{% page-ref page="../cloud-hosted-guide/create-a-btcp-pay-button.md" %}

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


