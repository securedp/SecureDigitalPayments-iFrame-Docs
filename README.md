<a href='https://smartpay.curexe.com'><img src="https://smartpay.curexe.com/resources/img/logo.png" width="200" ></a>

## Overview

The Secure Digital Payments Checkout solution consists of an iFrame, an API and the Secure Digital Payments website. This documentation covers the installation and use of the iFrame, which captures consumer detail which can then be accessed by retailers through the API.

<img src="diagram.png">

# Installing the iFrame

To install the Secure Digital Payments application on your website requires adding just one line of HTML: an iframe. [Need help with HTML?](https://www.w3schools.com/tags/tag_iframe.asp)

The iframe element itself can be customized using the HTML attributes of your choice. It's recommended that you set the border to 0, the width to 100% and the height to a fixed amount no less than 500 (to reduce scrolling).

The syntax for the iframe src is as follows:

```
https://staging-xmd84vwb.smartpay.curexe.com/iframe.php?parameter=value&meter=value (etc.)
```

As you can see, all of the input parameters in the iframe code are "dynamic" -- in other words, your application will need to populate them with the appropriate publisher/retailer or consumer information. All parameter/value pairs must be separated with an ampersand (&). All values should be URL-encoded.

# Input Parameters

The following input parameters are available for use in the iframe:

<table>
<thead>
<tr>
<th>Parameter <sup>1</sup></th>
<th>Mandatory <sup>2</sup></th>
<th>Description</th>
<th>Example</th>
</tr>
</thead>
<tbody>
<tr>
<td>key</td>
<td>Y</td>
<td>This is your unique, case-sensitive iframe key</td>
<td>abc123</td>
</tr>
<tr>
<td>singleAmt</td>
<td>N <sup>3</sup></td>
<td>A single amount to be charged at time of purchase</td>
<td>100.00</td>
</tr>
<tr>
<td>recurAmt</td>
<td>N <sup>3</sup></td>
<td>A recurring amount to be charged</td>
<td>100.00</td>
</tr>
<tr>
<td>recurFreq</td>
<td>N <sup>3</sup></td>
<td>Frequency of recurring billing. At this time, only “m” (monthly) is available.</td>
<td>m</td>
</tr>
<tr>
<td>recurStart</td>
<td>N <sup>3</sup></td>
<td>Date to start recurring billing</td>
<td>2018-01-01 12:00:00</td>
</tr>
<tr>
<td>curr</td>
<td>Y</td>
<td>Destination currency of transaction</td>
<td>CAD</td>
</tr>
<tr>
<td>firstName</td>
<td>N</td>
<td>Customer’s first name</td>
<td>John</td>
</tr>
<tr>
<td>lastName</td>
<td>N</td>
<td>Customer’s last name</td>
<td>Smith</td>
</tr>
<tr>
<td>address</td>
<td>N</td>
<td>Customer’s street address</td>
<td>123 Main Street</td>
</tr>
<tr>
<td>city</td>
<td>N</td>
<td>Customer’s city</td>
<td>New York</td>
</tr>
<tr>
<td>region</td>
<td>N</td>
<td>Customer’s state, province or other region</td>
<td>New York</td>
</tr>
<tr>
<td>country</td>
<td>N</td>
<td>Customer’s country</td>
<td>US</td>
</tr>
<tr>
<td>postalCode</td>
<td>N</td>
<td>Customer’s postal code</td>
<td>10001</td>
</tr>
<tr>
<td>email</td>
<td>N</td>
<td>Customer’s email address</td>
<td>john@smith.com</td>
</tr>
<tr>
<td>phone</td>
<td>N</td>
<td>Customer’s phone number</td>
<td>555-555-5555</td>
</tr>
</tbody>
</table>

<sup>1</sup> "Camelcase" has been used for visual clarity, but any case may be used when implemented.

<sup>2</sup> If mandatory input parameters aren't provided, the iframe will display an error message and fail to submit transactions.

<sup>3</sup> SingleAmt and recurAmt are individually non-mandatory, but one must be used. Also, if recurAmt is used, recurFreq and recurStart both become mandatory.
