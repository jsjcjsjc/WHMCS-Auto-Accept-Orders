把其中26行的 'autosetup' => false 改为 true
直接顺带解决了第二个余额支付无法自动开通的问题
```
apiuser – No need to add anything there as code is already done to get that value //不需要管
autosetup – determines whether product provisioning is performed //是否自动配置开启小鸡
sendregistrar – determines whether domain automation is performed //域名相关不用管
sendemail – sets if welcome emails for products and registration confirmation emails for domains should be sent //是否发送邮件
ispaid – set to true if you want to accept only paid orders //是否只自动处理已支付订单

In case you want it to auto execute the Module create command for the product with price 0.00 please uncomment the Line 48 to 50 
// 是否自动执行价格为0.00的商品 取消48~50行的注释
In case you want it to auto execute the Module create command and auto accept  for the Free product  please uncomment the Line 53 to 55
// 是否自动执行免费的商品 取消53~55行的注释
```
#For integration with your WHMCS, visit https://whmcsninja.com/ or email us at : whmcsninja@gmail.com
# WHMCS-Auto-Accept-Orders
This WHMCS Hook will auto accept orders. There is no need to manually accept them anymore ! No more “pending” orders…
Hook is highly customizable with a settings section that will let you set the following –

    Activate product provisioning (yes/no)
    Perform domain automation (yes/no)
    Send welcome email to client (yes/no)
    Accept only paid orders (yes/no)
    Set specific payment methods (i.e, “paypal”)
Installation

Edit it with your favourite code editor (we recommend notepad++).

In the begining of the hook file, you will find our settings section –

return array( 
	'apiuser'		=> '$admin->id, // Don't add anything Here
	'autosetup' 		=> false,
	'sendregistrar' 	=> false, 
	'sendemail' 		=> false, 
	'ispaid'		=> true, 
	'paymentmethod'		=> array(''), 
);

    apiuser – No need to add anything there as code is already done to get that value 
    autosetup – determines whether product provisioning is performed
    sendregistrar – determines whether domain automation is performed
    sendemail – sets if welcome emails for products and registration confirmation emails for domains should be sent
    ispaid – set to true if you want to accept only paid orders
    paymentmethod – set the payment method you want to accept automaticly (leave empty to use all payment methods). Payment method should be exactly as it named in WHMCS (copy & paste the gateway name)
    In case you want it to auto execute the Module create command for the product with price 0.00 please uncomment the Line 48 to 50 
    In case you want it to auto execute the Module create command and auto accept  for the Free product  please uncomment the Line 53 to 55 

Once you finished the editing the settings, upload it to your WHMCS hooks folder (“includes/hooks“).

Done:) !
