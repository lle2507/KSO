# API DOCUMENT
---
# A. ORO To CC
### 1. Change Order
>** POST api/Order/Change**
#### Parameters:
- CurrentDate: (CurrentDate - in Rule)
- PublicKey: (PublicKey - in Rule)
- Checksum: ([Checksum](#Checksum)- in Rule)
- Id: Order id
- OrderNumber: Order Number
- CreateDate: create order time date
- ModifyDate: modify order time date
- OrderStatus: (OrderStatus - in Rule)
- Payment: (Payment - in Rule)
- Total: total amount
- Remark: Order remark
- CustomerInfo: (CustomerInfo - in Rule)
- ProductList: (ProductList - in Rule)
```js
{
	"CurrentDate":"2017-12-01 10:20:11",
	"PublicKey":"PublicKey",
	"Checksum":"B84FF8057EE3A7F87DEAC4AE29AC59292F02E6C28F987031648011018384D888"
	"Id":"1",
	"OrderNumber":"SG0001",
	"CreateDate":"2017-12-01 10:20:11",
	"ModifyDate":"2017-12-01 10:21:11", 
	"OrderStatus":
			{"Id":"1", "Name":"Receive", "StatusDate":"2017-12-01 10:21:11"},
	"Payment":
			{"Id":"1", "Name":"Cash on Delivery"},
	"Total":5000000,
	"Remark":"abc"
	"CustomerInfo":
			{
				"Id":"1",
				"MailAddress":"abc@gmail.com",
				"Password":"123",
				"FirstName":"abc",
				"LastName":"abc",
				"Birthday":"1980-01-23",
				"Occupation":
							{"Id":"1","Name":""},
				"MobilePhone":"01923913002",
				"FixedPhone":"",
				"Address":"40/132",
				"Road":"Truong Chinh",
				"Ward":
							{"Id":"03","Name":"Phuong 1"},
				"District":
							{"Id":"123","Name":"Tan Binh"},
				"Province":
							{"Id":"456","Name":"HCM"},
				"Gender":"Male",
				"Remark":"abc",
				"Marrried":0,
				"ReceiveEmail":0,
				"ReceiveDM":0,
			},
	"ProductList":
			[{
				"Id":"1",
				"Name":"tivi",
				"Qty":1,
				"Price":50000,
				"Disount":1000,
				"Remark":"abc"
			}]	
}
```
#### Result:
- ErrorCode: (ErrorCode - in Rule)
- ErrorMessage: (ErrorMessage - in Rule)
```js
{
	"ErrorCode":"",
	"ErrorMessage":""
}
```
# B. CC To ORO
### 1. Get order
>** POST api/Order/Search**
#### Parameters:
- CurrentDate: (CurrentDate - in Rule) 
- PublicKey: (PublicKey - in Rule)
- Checksum: (Checksum - in Rule)
- PageSize: Page size
- CurrentPage: current page
- Id: Order id
- OrderNumber: Order Number
- CreateDateFrom: create order time date
- CreateDateTo: create order time date
```js
{
	"CurrentDate":"2017-12-01 10:20:11",
	"PublicKey":"PublicKey",
	"Checksum":"B84FF8057EE3A7F87DEAC4AE29AC59292F02E6C28F987031648011018384D888"
	"PageSize":10,
	"CurrentPage":1,
	"Id":"999",
	"OrderNumber":"",
	"CreateDateFrom":"",
	"CreateDateTo":""	
}
```
#### Result:
- ErrorCode: (ErrorCode - Rule)
- ErrorMessage: (ErrorMessage - Rule)
- Data: (DataSearchOrder - in Rule)
```js
{
	"ErrorCode":"",
	"ErrorMessage":"",
	"Data":
		{
			"TotalRow":130,
			"PageSize":10,
			"CurrentPage":1,
			"OrderList":
					[{
						"Id":"1",
						"OrderNumber":"SG0001",
						"CreateDate":"2017-12-01 10:20:11",
						"ModifyDate":"2017-12-01 10:21:11", 
						"OrderStatus":
								{"Id":"1", "Name":"Receive", "StatusDate":"2017-12-01 10:21:11"},
						"Payment":
								{"Id":"1", "Name":"Cash on Delivery"},
						"Total":5000000,
						"Remark":"abc"
						"CustomerInfo":
								{
									"Id":"1",
									"MailAddress":"abc@gmail.com",
									"Password":"123",
									"FirstName":"abc",
									"LastName":"abc",
									"Birthday":"1980-01-23",
									"Occupation":
												{"Id":"1","Name":""},
									"MobilePhone":"01923913002",
									"FixedPhone":"",
									"Address":"40/132",
									"Road":"Truong Chinh",
									"Ward":
												{"Id":"03","Name":"Phuong 1"},
									"District":
												{"Id":"123","Name":"Tan Binh"},
									"Province":
												{"Id":"456","Name":"HCM"},
									"Gender":"Male",
									"Remark":"abc",
									"Marrried":0,
									"ReceiveEmail":0,
									"ReceiveDM":0,
								},
						"ProductList":
								[{
									"Id":"1",
									"Name":"tivi",
									"Qty":1,
									"Price":50000,
									"Disount":1000,
									"Remark":"abc"
								}]
					}]
		}
}
``` 
# Rule
### 1. PrivateKey
- PrivateKey:  
### 2. PublicKey
- PublicKey: 
<a name="Checksum"></a>
## 3. Checksum ##
** Checksum = SHA256(CurrentDate + PublicKey + PrivateKey)**
### 4. CurrentDate
- Current request time date
### 5. ErrorCode
- 0: Success
- !=0: Fail
### 6. ErrorMessage
- Error description
### 7. OrderInfo
- Id: Order id
- OrderNumber: Order Number
- CreateDate: create order time date
- ModifyDate: modify order time date
- OrderStatus: (OrderStatus - in Rule)
- Payment: (Payment - in Rule)
- Total: total amount
- Remark: Order remark
- CustomerInfo: (CustomerInfo - in Rule)
- ProductList: (ProductList - in Rule)
```js
{
	"Id":"1",
	"OrderNumber":"SG0001",
	"CreateDate":"2017-12-01 10:20:11",
	"ModifyDate":"2017-12-01 10:21:11", 
	"OrderStatus":
			{"Id":"1", "Name":"Receive", "StatusDate":"2017-12-01 10:21:11"},
	"Payment":
			{"Id":"1", "Name":"Cash on Delivery"},
	"Total":5000000,
	"Remark":"abc"
	"CustomerInfo":
			{
				"Id":"1",
				"MailAddress":"abc@gmail.com",
				"Password":"123",
				"FirstName":"abc",
				"LastName":"abc",
				"Birthday":"1980-01-23",
				"Occupation":
							{"Id":"1","Name":""},
				"MobilePhone":"01923913002",
				"FixedPhone":"",
				"Address":"40/132",
				"Road":"Truong Chinh",
				"Ward":
							{"Id":"03","Name":"Phuong 1"},
				"District":
							{"Id":"123","Name":"Tan Binh"},
				"Province":
							{"Id":"456","Name":"HCM"},
				"Gender":"Male",
				"Remark":"abc",
				"Marrried":0,
				"ReceiveEmail":0,
				"ReceiveDM":0,
			},
	"ProductList":
			[{
				"Id":"1",
				"Name":"tivi",
				"Qty":1,
				"Price":50000,
				"Disount":1000,
				"Remark":"abc"
			}]
}
```
### 8. Orderstatus
- Id: Status Id
- Name: Status name
- StatusDate: order status time date
```js
{
	"Id":"1", 
	"Name":"Receive", 
	"StatusDate":"2017-12-01 10:21:11"
}
```
### 9. Payment
- Id: Payment Id
- Name: Payment name 
```js
{
	"Id":"1", 
	"Name":"Receive"
}
```
### 10. ProductList
- Id: Product Id
- Name: Product Name
- Qty: Quantity
- Price: Unit price
- Discount: Discount amount
- Remark: Product remark
``` js
[{
	"Id":"1",
	"Name":"tivi",
	"Qty":1,
	"Price":50000,
	"Disount":1000,
	"Remark":"abc"
}]
```
### 11. CustomerInfo
``` js
{
	"Id":"1",
	"MailAddress":"abc@gmail.com",
	"Password":"123",
	"FirstName":"abc",
	"LastName":"abc",
	"Birthday":"1980-01-23",
	"Occupation":
				{"Id":"1","Name":""},
	"MobilePhone":"01923913002",
	"FixedPhone":"",
	"Address":"40/132",
	"Road":"Truong Chinh",
	"Ward":
				{"Id":"03","Name":"Phuong 1"},
	"District":
				{"Id":"123","Name":"Tan Binh"},
	"Province":
				{"Id":"456","Name":"HCM"},
	"Gender":"Male",
	"Remark":"abc",
	"Marrried":0,
	"ReceiveEmail":0,
	"ReceiveDM":0,
}
```
### 12. DataSearchOrder
- TotalRow: total rows
- PageSize: current page size
- CurrentPage: current page
- OrderList: Orders list (OrderInfo - in Rule)
``` js
{
	"TotalRow":130,
	"PageSize":10,
	"CurrentPage":1,
	"OrderList":
			[{
				"Id":"1",
				"OrderNumber":"SG0001",
				"CreateDate":"2017-12-01 10:20:11",
				"ModifyDate":"2017-12-01 10:21:11", 
				"OrderStatus":
						{"Id":"1", "Name":"Receive", "StatusDate":"2017-12-01 10:21:11"},
				"Payment":
						{"Id":"1", "Name":"Cash on Delivery"},
				"Total":5000000,
				"Remark":"abc"
				"CustomerInfo":
						{
							"Id":"1",
							"MailAddress":"abc@gmail.com",
							"Password":"123",
							"FirstName":"abc",
							"LastName":"abc",
							"Birthday":"1980-01-23",
							"Occupation":
										{"Id":"1","Name":""},
							"MobilePhone":"01923913002",
							"FixedPhone":"",
							"Address":"40/132",
							"Road":"Truong Chinh",
							"Ward":
										{"Id":"03","Name":"Phuong 1"},
							"District":
										{"Id":"123","Name":"Tan Binh"},
							"Province":
										{"Id":"456","Name":"HCM"},
							"Gender":"Male",
							"Remark":"abc",
							"Marrried":0,
							"ReceiveEmail":0,
							"ReceiveDM":0,
						},
				"ProductList":
						[{
							"Id":"1",
							"Name":"tivi",
							"Qty":1,
							"Price":50000,
							"Disount":1000,
							"Remark":"abc"
						}]
			}]
}
```

