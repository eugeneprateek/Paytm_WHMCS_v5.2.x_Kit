# Introduction

This integration kit is used in WHMCS PHP E-Commerce Application. This library provides support for Paytm payment gateway.

# Installation

Copy the files from this plugin into the corresponding folders on your installation, as mentioned below:
 1. Copy the Paytm/gateways/paytm.php file into your installation's /module/gateways/ folder
 2. Copy the Paytm/gateways/callback/paytm.php file into your installation's /module/gateways/callback folder.
 3. Copy the Paytm/gateways/paytm-sdk folder into your /module/gateways folder

# Configuration

Provide the values for the following in the *Configuration Settings* of the Admin Panel.
 1. Merchant ID
 2. Website
 3. Merchant Key
 4. Channel ID
 5. Industry Type ID

Edit gateways/callback/paytm.php with a text editor such as notepad or notepad++ and modify following two lines
$filename = $protocol . $host . '/whmcs/viewinvoice.php?id=' . $txnid . '&paymentsuccess=true';
$location = $protocol . $host . '/whmcs/viewinvoice.php?id=' . $txnid . '&paymentfailed=true';

Explanation 
If your whmcs is installed directly on the root domain for example abc.com you need to remove /whmcs from both the lines.
Example : 
$filename = $protocol . $host . '/viewinvoice.php?id=' . $txnid . '&paymentsuccess=true';
$location = $protocol . $host . '/viewinvoice.php?id=' . $txnid . '&paymentfailed=true';


If your whmcs is installed on a sub folder such as abc.com/billing you need to replace whmcs with your folder name.
$filename = $protocol . $host . '/billing/viewinvoice.php?id=' . $txnid . '&paymentsuccess=true';
$location = $protocol . $host . '/billing/viewinvoice.php?id=' . $txnid . '&paymentfailed=true';
