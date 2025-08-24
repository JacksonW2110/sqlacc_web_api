## API Documentation

#### API Testing with Postman

#### Get JWT Token
- JWT Token expires every 30 minutes
- Call API endpoint => {{baseUrl}}/api/Auth/login with the login object attach to request body
```
  "email": "EMAIL",
  "password": "PASSWORD"
```
<img width="830" height="314" alt="image" src="https://github.com/user-attachments/assets/1acd2f00-0e77-4d48-8286-0ee407fdf557" />

Result:
![image](https://github.com/user-attachments/assets/614c57c8-904c-4e23-84fa-561239f47eb8)

#### Attach the JWT Bearer Token for each API request
![image](https://github.com/user-attachments/assets/9cd4541a-73cb-46cc-ba98-c53a57975d44)

### Customer
#### Get All Customers
- Get All Customers from SQL Accounting Database
- Call API endpoint => {{baseUrl}}/api/Customers/GetAllCustomers
  <img width="822" height="328" alt="image" src="https://github.com/user-attachments/assets/4a24ea3e-702b-4405-b5b4-c26adad9b002" />

- Result:
  ![image](https://github.com/user-attachments/assets/a2060094-92e0-4491-a077-033ebe6f0edb)

#### Add Customer
- Add Customer to SQL Accounting Database
- Call API endpoint => {{baseUrl}}/api/Customers/AddCustomer with the object attach to request body
  ```
  {
    "code": "string",
    "controlaccount": "string",
    "companyname": "string",
    "area": "string",
    "agent": "string",
    "creditterm": "string",
    "creditlimit": 0,
    "overduelimit": 0,
    "currencycode": "string",
    "outstanding": 0,
    "addCustomerBranchRequestDtos": [
      {
        "code": "string",
        "branchname": "string",
        "addresS1": "string",
        "addresS2": "string",
        "attention": "string",
        "phonE1": "string",
        "email": "string"
      }
    ]
  }
  ```
  <img width="824" height="716" alt="image" src="https://github.com/user-attachments/assets/e56fe781-5147-41c1-8a79-454a01f03112" />

- Result:
  ![image](https://github.com/user-attachments/assets/685b3ce3-8efe-418e-993c-ae4edf947ed0)

### Update Customer 
- Update Customer to SQL Accounting Database
- Call API endpoint => {{baseUrl}}/api/Customers/UpdateCustomer/{customerCode} with the object attach to request body
```
{
  "code": "string",
  "controlaccount": "string",
  "companyname": "string",
  "area": "string",
  "agent": "string",
  "creditterm": "string",
  "creditlimit": 0,
  "overduelimit": 0,
  "currencycode": "string",
  "outstanding": 0,
  "updateCustomerBranchRequestDtos": [
    {
      "code": "string",
      "branchname": "string",
      "addresS1": "string",
      "addresS2": "string",
      "attention": "string",
      "phonE1": "string",
      "email": "string"
    }
  ]
}
```
  <img width="1212" height="723" alt="image" src="https://github.com/user-attachments/assets/70337ead-88cb-4a8f-9718-deb1e5a09cc3" />

- Result
  ![image](https://github.com/user-attachments/assets/8b737a60-5c5e-4815-a658-907f89458342)

#### Get Customer By Code
- Get Customer from SQL Accounting Database by Code
- Call API endpoint => {{baseUrl}}/api/Customers/GetCustomerByCode/{customerCode}
  <img width="928" height="375" alt="image" src="https://github.com/user-attachments/assets/43265d42-7ef6-4aee-b061-fe50cbf3e508" />

- Result:
  ![image](https://github.com/user-attachments/assets/91d722d7-f742-4722-a4f7-973976fd19d4)

#### Delete Customer
- Delete Customer from SQL Accounting Database
- Call API endpoint => {{baseUrl}}/api/Customers/DeleteCustomer/{customerCode}
  <img width="864" height="336" alt="image" src="https://github.com/user-attachments/assets/4fbca911-8ec0-4841-a148-6b4f65034a72" />

- Result:
  ![image](https://github.com/user-attachments/assets/0e5d055b-eec7-4e9c-a906-c1b0e50e5430)

### Item
#### Get All Items
- Get All Items from SQL Accounting Database
- Call API endpoint => {{baseUrl}}/api/Items/GetAllItems
  <img width="857" height="364" alt="image" src="https://github.com/user-attachments/assets/ca018e0d-3474-4357-a17f-e2c55254a9c5" />

- Result:
  ![image](https://github.com/user-attachments/assets/d023fc98-cd34-4711-b6eb-1228c5508431)

#### Add Item
- Add Item to SQL Accounting Database
- Call API endpoint => {{baseUrl}}/api/Items/CreateItem with the object attach to request body
- Make sure the StockGroup already existed in SQL Accounting
```
{
  "code": "string",
  "description": "string",
  "stockgroup": "string",
  "stockcontrol": true,
  "costingmethod": 0,
  "addItemUomRequestDtos": [
    {
      "uom": "string",
      "rate": 0,
      "refcost": 0,
      "refprice": 0,
      "isbase": true
    }
  ]
}
```
  <img width="821" height="553" alt="image" src="https://github.com/user-attachments/assets/6c433a71-1114-411a-af59-52639750ca66" />

- Result:
  ![image](https://github.com/user-attachments/assets/4aa8ba7b-f026-4469-980e-52d6dfff811c)

#### Update Item
- Update Item to SQL Accounting Database
- Call API endpoint => {{baseUrl}}/api/Items/UpdateItem/{itemCode} with object attach to request body
- Make sure the StockGroup already existed in SQL Accounting
  ```
  {
    "code": "string",
    "description": "string",
    "stockgroup": "string",
    "stockcontrol": true,
    "costingmethod": 0,
    "updateItemUomRequestDtos": [
      {
        "uom": "string",
        "rate": 0,
        "refcost": 0,
        "refprice": 0,
        "isbase": true
      }
    ]
  }
  ```
  <img width="1054" height="559" alt="image" src="https://github.com/user-attachments/assets/6b336f89-51e0-4cc0-a9a6-f399a7f80c0f" />

- Result:
  ![image](https://github.com/user-attachments/assets/89de4fcb-7069-41d1-9ac3-2733b9aca289)

#### Get Item by ItemCode
- Get Item by ItemCode from SQL Accounting Database
- Call API endpoint => {{baseUrl}}/api/Items/GetItemByItemCode/{itemCode}
  <img width="879" height="347" alt="image" src="https://github.com/user-attachments/assets/d607d0c6-075b-42e7-ab54-450b290238de" />

- Result:
  ![image](https://github.com/user-attachments/assets/a88de8bc-8999-4a8f-a352-b12da4e196a7)

#### Delete Item
- Delete Item from SQL Accounting Database
- Call API endpoint => {{baseUrl}}/api/Items/DeleteItem/{itemCode}
  <img width="924" height="351" alt="image" src="https://github.com/user-attachments/assets/dce1d61d-ac39-4971-918e-5c144e42c288" />

- Result:
  ![image](https://github.com/user-attachments/assets/63f488dd-e81c-49c0-9be5-467454e753bb)

### SalesInvoice
#### Get All SalesInvoices
- Get all SalesInvoices from SQL Accounting Database
- Call API endpoint => {{baseUrl}}/api/SalesInvoices/GetAllSalesInvoices
  <img width="949" height="334" alt="image" src="https://github.com/user-attachments/assets/616ae430-f47b-4a9e-b3c9-c337e4a483be" />

- Result:
  ![image](https://github.com/user-attachments/assets/4d9f7e49-7852-43cb-9a7f-f59c91e14391)
  ![image](https://github.com/user-attachments/assets/4a68f759-090b-4a30-b93f-502559a96837)

#### Create SalesInvoice
- Create SalesInvoice in SQL Accounting Database
- Call API endpoint => {{baseUrl}}/api/SalesInvoices/CreateSalesInvoice with object attach to request body
- Make sure the customer existed in SQL Accounting Database
  ```
  {
    "docno": "string",
    "docdate": "2025-06-13",
    "code": "string",
    "project": "string",
    "docamt": 0,
    "addSalesInvoiceDetailRequestDtos": [
      {
        "itemcode": "string",
        "description": "string",
        "qty": 0,
        "uom": "string",
        "unitprice": 0,
        "disc": "string",
        "tax": "string",
        "taxrate": "string",
        "taxinclusive": true
      }
    ]
  }
  ```
  <img width="1036" height="698" alt="image" src="https://github.com/user-attachments/assets/6d369ecd-37e7-4874-b597-acab05da9c70" />

- Result:
  ![image](https://github.com/user-attachments/assets/84a1fd6c-6cb2-40d7-ae70-c7c2c6a8c386)
  ![image](https://github.com/user-attachments/assets/dd845e5d-a5a2-4ebd-9ff6-9e329eaa00a4)

#### Update SalesInvoice
- Update SalesInvoice in SQL Accounting Database
- Call API endpoint => {{baseUrl}}/api/SalesInvoices/UpdateSalesInvoice/{invoiceNo} with object attach to request body
- Make sure the customer existed in SQL Accounting Database
  ```
  {
    "docdate": "2025-06-13",
    "code": "string",
    "project": "string",
    "docamt": 0,
    "updateSalesInvoiceDetailRequestDtos": [
      {
        "itemcode": "string",
        "description": "string",
        "qty": 0,
        "uom": "string",
        "unitprice": 0,
        "disc": "string",
        "tax": "string",
        "taxrate": "string",
        "taxinclusive": true
      }
    ]
  }
  ```
  <img width="1140" height="678" alt="image" src="https://github.com/user-attachments/assets/d69ede57-2d69-4167-9fc8-cdd32aacce3d" />

- Result
  ![image](https://github.com/user-attachments/assets/1aaa6cfc-da41-409c-8543-82842bef1a24)
  ![image](https://github.com/user-attachments/assets/4044d120-7543-4719-8829-ac2ffd5342fa)

#### Get SalesInvoice by InvoiceNo
- Get SalesInvoice by InvoiceNo from SQL Accounting Database
- Call API endpoint => {{baseUrl}}/api/SalesInvoices/GetSalesInvoiceByDocNo/{invoiceNo}
  <img width="882" height="367" alt="image" src="https://github.com/user-attachments/assets/b0b54441-3de7-4eb7-85d7-d5cefd5a307f" />

- Result:
  ![image](https://github.com/user-attachments/assets/5060c8c1-7f8e-4864-a79b-2e84bdc68107)
  ![image](https://github.com/user-attachments/assets/0317ba03-651f-4968-a7bc-51d35120dff1)

#### Delete SalesInvoice
- Delete SalesInvoice in SQL Accounting Database
- Call API endpoint => {{baseUrl}}/api/SalesInvoices/DeleteSalesInvoice/{invoiceNo}
  <img width="904" height="336" alt="image" src="https://github.com/user-attachments/assets/d60a1b08-487e-4824-8883-8db5ed754f62" />

- Result:
  ![image](https://github.com/user-attachments/assets/c187a913-24dc-4275-82d8-f8cd82d8590e)


### CashSales
#### Get All CashSales
- Get all CashSales from SQL Accounting Database
- Call API endpoint => {{baseUrl}}/api/CashSales/GetAllCashSales
  <img width="1605" height="420" alt="image" src="https://github.com/user-attachments/assets/08c9624d-ca12-413c-a974-00e620386cb2" />


- Result:
  <img width="1593" height="935" alt="image" src="https://github.com/user-attachments/assets/5bcc8f69-3c6e-4a69-beb6-a67d3b0f2524" />
  <img width="1639" height="948" alt="image" src="https://github.com/user-attachments/assets/ac455298-2e4d-410b-bd16-217f45bf0ce4" />

#### Create CashSales
- Create CashSales in SQL Accounting Database
- Call API endpoint => {{baseUrl}}/api/CashSales/CreateCashSales with object attach to request body
- Make sure the customer existed in SQL Accounting Database
  ```
  {
    "docno": "string",
    "docdate": "2025-08-23",
    "code": "string",
    "project": "string",
    "docamt": 0,
    "addCashSalesDetailRequestDtos": [
      {
        "itemcode": "string",
        "description": "string",
        "qty": 0,
        "uom": "string",
        "unitprice": 0,
        "disc": "string",
        "tax": "string",
        "taxrate": "string",
        "taxamt": 0,
        "taxinclusive": true
      }
    ]
  }
  ```
  <img width="1588" height="1183" alt="image" src="https://github.com/user-attachments/assets/8e8ecb22-87f2-4c18-bd3f-be613b3bb824" />

- Result:
  <img width="1593" height="1032" alt="image" src="https://github.com/user-attachments/assets/54110eca-6549-431a-89c0-469e1f26cc11" />
  <img width="1570" height="1079" alt="image" src="https://github.com/user-attachments/assets/bd9249e2-f226-443a-bd57-9271b850f89c" />

#### Update CashSales
- Update CashSales in SQL Accounting Database
- Call API endpoint => {{baseUrl}}/api/CashSales/UpdateCashSales/{docNo} with object attach to request body
- Make sure the customer existed in SQL Accounting Database
  ```
  {
    "docdate": "2025-08-23",
    "code": "string",
    "project": "string",
    "docamt": 0,
    "updateCashSalesDetailRequestDtos": [
      {
        "itemcode": "string",
        "description": "string",
        "qty": 0,
        "uom": "string",
        "unitprice": 0,
        "disc": "string",
        "tax": "string",
        "taxrate": "string",
        "taxamt": 0,
        "taxinclusive": true
      }
    ]
  }
  ```
  <img width="1566" height="1178" alt="image" src="https://github.com/user-attachments/assets/c237ec1c-fdd1-44b0-bfe0-5d463954dd9b" />

- Result
  <img width="1568" height="932" alt="image" src="https://github.com/user-attachments/assets/f58e9c6b-5b92-451c-befa-68a1be981971" />
  <img width="1594" height="922" alt="image" src="https://github.com/user-attachments/assets/d5349e19-1515-491f-b133-0ece37c1d055" />
  <img width="1588" height="931" alt="image" src="https://github.com/user-attachments/assets/690bc549-e31f-460a-b079-0767fa71ed85" />

#### Get CashSales by DocNo
- Get CashSales by DocNo from SQL Accounting Database
- Call API endpoint => {{baseUrl}}/api/CashSales/GetCashSalesByDocNo/{docNo}
  <img width="1613" height="469" alt="image" src="https://github.com/user-attachments/assets/95ce6603-196e-4954-bce3-828f08071c68" />

- Result:
  <img width="1564" height="918" alt="image" src="https://github.com/user-attachments/assets/d21b2f4d-67fb-4ace-845e-05e6c7c5a779" />
  <img width="1620" height="932" alt="image" src="https://github.com/user-attachments/assets/06655c22-dadb-416d-821b-7b6bc547dcd8" />
  <img width="1583" height="898" alt="image" src="https://github.com/user-attachments/assets/79318b05-b55b-431c-8723-2c33f7975bef" />


#### Delete CashSales
- Delete CashSales in SQL Accounting Database
- Call API endpoint => {{baseUrl}}/api/CashSales/DeleteCashSales/{docNo}
  <img width="1609" height="533" alt="image" src="https://github.com/user-attachments/assets/1a9bde0f-149a-49ea-864d-0a73c825a568" />

- Result:
  <img width="1625" height="438" alt="image" src="https://github.com/user-attachments/assets/c3836d13-dba3-46c6-94b9-3eceb4e067a8" />

  
### CustomerPayment
#### Get All CustomerPayments
- Get all CustomerPayments from SQL Accounting Database
- Call API endpoint => {{baseUrl}}/api/CustomerPayments/GetAllCustomerPayments
  <img width="810" height="256" alt="image" src="https://github.com/user-attachments/assets/917a0a20-cfb3-4cff-837b-16a9ebed8a65" />

- Result:
  <img width="818" height="598" alt="image" src="https://github.com/user-attachments/assets/41bbc65c-60ad-444e-a900-068bcf0bcc7a" />

#### Create CustomerPayment
- Create CustomerPayment in SQL Accounting Database
- Call API endpoint => {{baseUrl}}/api/CustomerPayments/CreateCustomerPayment with object attach to request body
- Make sure the customer existed in SQL Accounting Database
  ```
  {
    "docno": "string",
    "code": "string",
    "docdate": "2025-08-22",
    "paymentmethodname": "string",
    "docamt": 0,
    "knockoffivno": "string",
    "knockoffamt": 0
  }
  ```
  <img width="821" height="320" alt="image" src="https://github.com/user-attachments/assets/e9064277-917d-4cd1-89d8-fcaafd39bc8c" />

- Result:
  <img width="810" height="325" alt="image" src="https://github.com/user-attachments/assets/bb4ce3e9-b2a6-4641-bfdd-73166dfbbd71" />

#### Update CustomerPayment
- Update CustomerPayment in SQL Accounting Database
- Call API endpoint => {{baseUrl}}/api/CustomerPayments/UpdateCustomerPayment/{docNo} with object attach to request body
- Make sure the customer existed in SQL Accounting Database
  ```
  {
    "docno": "string",
    "code": "string",
    "docdate": "2025-08-22",
    "paymentmethodname": "string",
    "docamt": 0,
    "knockoffivno": "string",
    "knockoffamt": 0
  }
  ```
  <img width="1602" height="640" alt="image" src="https://github.com/user-attachments/assets/5b96c5ee-6dea-45aa-9984-544f9cb05985" />

- Result
  <img width="1635" height="664" alt="image" src="https://github.com/user-attachments/assets/d211c1eb-bc65-423a-b01a-5e3fc92dcb30" />

#### Get CustomerPayment by DocNo
- Get CustomerPayment by DocNo from SQL Accounting Database
- Call API endpoint => {{baseUrl}}/api/CustomerPayments/GetCustomerPaymentByDocNo/{docNo}
  <img width="1588" height="540" alt="image" src="https://github.com/user-attachments/assets/472d5065-cc98-4990-8ef9-ed8384817256" />

- Result:
  <img width="1593" height="659" alt="image" src="https://github.com/user-attachments/assets/e4fce78d-74ad-48ab-8935-caf5145d6407" />

  
#### Delete CustomerPayment
- Delete CustomerPayment in SQL Accounting Database
- Call API endpoint => {{baseUrl}}/api/CustomerPayments/DeleteCustomerPayment/{docNo}
  <img width="1604" height="519" alt="image" src="https://github.com/user-attachments/assets/745285fe-dc30-4961-be3f-a653e4bdaf03" />

- Result:
  <img width="1606" height="379" alt="image" src="https://github.com/user-attachments/assets/bf03fbe7-db73-4251-8064-11b8b979a93f" />


### Supplier
#### Get All Suppliers
- Get All Suppliers from SQL Accounting Database
- Call API endpoint => {{baseUrl}}/api/Suppliers/GetAllSuppliers
  <img width="1606" height="495" alt="image" src="https://github.com/user-attachments/assets/bfdf75d1-b71a-4b64-a7e7-62915958b8f7" />

- Result:
  <img width="1601" height="951" alt="image" src="https://github.com/user-attachments/assets/b93cd7b0-9adb-4dea-920d-2afc7fdfac04" />
  <img width="1610" height="954" alt="image" src="https://github.com/user-attachments/assets/26acb815-3684-4ef0-9812-e1c1e1d04cb9" />

#### Add Supplier
- Add Supplier to SQL Accounting Database
- Call API endpoint => {{baseUrl}}/api/Suppliers/AddSupplier with the object attach to request body
  ```
  {
    "code": "string",
    "controlaccount": "string",
    "companyname": "string",
    "area": "string",
    "agent": "string",
    "creditterm": "string",
    "creditlimit": 0,
    "overduelimit": 0,
    "currencycode": "string",
    "outstanding": 0,
    "addSupplierBranchRequestDtos": [
      {
        "code": "string",
        "branchname": "string",
        "addresS1": "string",
        "addresS2": "string",
        "attention": "string",
        "phonE1": "string",
        "email": "string"
      }
    ]
  }
  ```
  <img width="1590" height="1183" alt="image" src="https://github.com/user-attachments/assets/f28ab304-f127-40cc-afed-7f49d5d1257f" />

- Result:
  <img width="1592" height="852" alt="image" src="https://github.com/user-attachments/assets/f86b98b5-6482-4154-889b-369586a08767" />
  <img width="1582" height="836" alt="image" src="https://github.com/user-attachments/assets/7500fcb3-43a5-4b26-959c-7390378f736f" />

### Update Supplier
- Update Supplier to SQL Accounting Database
- Call API endpoint => {{baseUrl}}/api/Suppliers/UpdateSupplier/{supplierCode} with the object attach to request body
  ```
  {
    "code": "string",
    "controlaccount": "string",
    "companyname": "string",
    "area": "string",
    "agent": "string",
    "creditterm": "string",
    "creditlimit": 0,
    "overduelimit": 0,
    "currencycode": "string",
    "outstanding": 0,
    "updateSupplierBranchRequestDtos": [
      {
        "code": "string",
        "branchname": "string",
        "addresS1": "string",
        "addresS2": "string",
        "attention": "string",
        "phonE1": "string",
        "email": "string"
      }
    ]
  }
  ```
  <img width="1581" height="1177" alt="image" src="https://github.com/user-attachments/assets/1a087fcd-847a-4871-ad1d-8ba289054ebc" />

- Result:
  <img width="1570" height="1065" alt="image" src="https://github.com/user-attachments/assets/aa115742-8173-47ab-af24-d9601b94aba0" />
  <img width="1589" height="1068" alt="image" src="https://github.com/user-attachments/assets/df698aa9-ba67-4271-b692-dbf02bacf6e7" />

#### Get Supplier By Code
- Get Supplier from SQL Accounting Database by Code
- Call API endpoint => {{baseUrl}}/api/Suppliers/GetSupplierrByCode/{supplierCode}
  <img width="1609" height="439" alt="image" src="https://github.com/user-attachments/assets/9fca4de4-bae0-485a-a873-2046225ad892" />

- Result:
  <img width="1577" height="953" alt="image" src="https://github.com/user-attachments/assets/3d2e2c18-07be-45ea-8ad6-c77eb6d696d4" />


#### Delete Supplier
- Delete Supplier from SQL Accounting Database
- Call API endpoint => {{baseUrl}}/api/Suppliers/DeleteSupplier/{supplierCode}
  <img width="1590" height="506" alt="image" src="https://github.com/user-attachments/assets/9794e916-1397-483e-9cfe-a0596a7811d5" />

- Result:
  <img width="1607" height="452" alt="image" src="https://github.com/user-attachments/assets/f56b8a0b-326d-492b-b736-e36a3841fb60" />


### PurchaseInvoice
#### Get All PurchaseInvoices
- Get all PurchaseInvoices from SQL Accounting Database
- Call API endpoint => {{baseUrl}}/api/PurchaseInvoices/GetAllPurchaseInvoices
  <img width="1600" height="388" alt="image" src="https://github.com/user-attachments/assets/348ee2b8-8812-4425-bbbf-bff577abf67b" />

- Result:
  <img width="1595" height="897" alt="image" src="https://github.com/user-attachments/assets/e7c2036e-b777-48d5-8501-f4df8335400e" />
  <img width="1612" height="959" alt="image" src="https://github.com/user-attachments/assets/5b153ec0-bb87-4157-92f9-ba73f278a41f" />


#### Create PurchaseInvoice
- Create PurchaseInvoice in SQL Accounting Database
- Call API endpoint => {{baseUrl}}/api/PurchaseInvoices/CreatePurchaseInvoice with object attach to request body
- Make sure the customer existed in SQL Accounting Database
  ```
  {
    "docno": "string",
    "docdate": "2025-08-24",
    "code": "string",
    "project": "string",
    "docamt": 0,
    "addPurchaseInvoiceDetailRequestDtos": [
      {
        "itemcode": "string",
        "description": "string",
        "qty": 0,
        "uom": "string",
        "unitprice": 0,
        "disc": "string",
        "tax": "string",
        "taxrate": "string",
        "taxamt": 0,
        "taxinclusive": true
      }
    ]
  }
  ```
  <img width="1609" height="1200" alt="image" src="https://github.com/user-attachments/assets/91117beb-e529-4708-bfe4-5e1463ccc43a" />
  
- Result:
  <img width="1601" height="1059" alt="image" src="https://github.com/user-attachments/assets/8227a76e-b69e-439a-aea7-6685852db82e" />
  <img width="1604" height="1071" alt="image" src="https://github.com/user-attachments/assets/bf36c61e-4d86-4e4f-b461-f2101b0eb27d" />

#### Update PurchaseInvoice
- Update PurchaseInvoice in SQL Accounting Database
- Call API endpoint => {{baseUrl}}/api/PurchaseInvoices/UpdatePurchaseInvoice/{invoiceNo} with object attach to request body
- Make sure the customer existed in SQL Accounting Database
  ```
  {
    "docdate": "2025-08-24",
    "code": "string",
    "project": "string",
    "docamt": 0,
    "updatePurchaseInvoiceDetailRequestDtos": [
      {
        "itemcode": "string",
        "description": "string",
        "qty": 0,
        "uom": "string",
        "unitprice": 0,
        "disc": "string",
        "tax": "string",
        "taxrate": "string",
        "taxamt": 0,
        "taxinclusive": true
      }
    ]
  }
  ```
  <img width="1605" height="1321" alt="image" src="https://github.com/user-attachments/assets/d83b8972-4a54-4dab-b687-8b03bb0c8c7e" />

- Result
  <img width="1577" height="998" alt="image" src="https://github.com/user-attachments/assets/c33c3c57-d525-47a0-bfd0-755b6523d691" />
  <img width="1584" height="1000" alt="image" src="https://github.com/user-attachments/assets/5f6d1ab3-21f8-4b95-b526-6a12fecf2c10" />

#### Get PurchaseInvoice by InvoiceNo
- Get PurchaseInvoice by InvoiceNo from SQL Accounting Database
- Call API endpoint => {{baseUrl}}/api/PurchaseInvoices/GetPurchaseInvoiceByDocNo/{invoiceNo}
  <img width="1595" height="497" alt="image" src="https://github.com/user-attachments/assets/4a370cc7-f9fb-4912-8b13-e79ba2151293" />

- Result:
  <img width="1606" height="1044" alt="image" src="https://github.com/user-attachments/assets/f6de8a16-0bfb-4838-91de-38b5fcd512b2" />
  <img width="1602" height="1036" alt="image" src="https://github.com/user-attachments/assets/3478c628-5b23-49ed-93ee-7d9684740c34" />

#### Delete PurchaseInvoice
- Delete PurchaseInvoice in SQL Accounting Database
- Call API endpoint => {{baseUrl}}/api/PurchaseInvoices/DeletePurchaseInvoice/{invoiceNo}
  <img width="1591" height="521" alt="image" src="https://github.com/user-attachments/assets/c2ea5b93-9ca9-409a-8513-e39d4e028fac" />

- Result:
  <img width="1608" height="419" alt="image" src="https://github.com/user-attachments/assets/757a00bc-ecc8-4c6b-b57f-4e53b8bec599" />


### SupplierPayment
#### Get All SupplierPayments
- Get all SupplierPayments from SQL Accounting Database
- Call API endpoint => {{baseUrl}}/api/SupplierPayments/GetAllSupplierPayments
  <img width="1621" height="515" alt="image" src="https://github.com/user-attachments/assets/8d6c9188-07ff-4748-8a5e-d86d96ff66a2" />

- Result:
  <img width="1606" height="1201" alt="image" src="https://github.com/user-attachments/assets/c4810610-fb20-4935-98c7-476739c666f1" />

#### Create SupplierPayment
- Create SupplierPayment in SQL Accounting Database
- Call API endpoint => {{baseUrl}}/api/SupplierPayments/AddSupplierPayment with object attach to request body
- Make sure the customer existed in SQL Accounting Database
  ```
  {
    "docno": "string",
    "code": "string",
    "docdate": "2025-08-24",
    "paymentmethodname": "string",
    "docamt": 0,
    "knockoffivno": "string",
    "knockoffamt": 0
  }
  ```
  <img width="1586" height="716" alt="image" src="https://github.com/user-attachments/assets/ec4925b3-5cda-4669-9cf8-f149c58145ff" />

- Result:
  <img width="1638" height="685" alt="image" src="https://github.com/user-attachments/assets/f7f6401b-424a-458e-81cc-bcc0492e062e" />


#### Update SupplierPayment
- Update SupplierPayment in SQL Accounting Database
- Call API endpoint => {{baseUrl}}/api/SupplierPayments/UpdateSupplierPayment/{docNo} with object attach to request body
- Make sure the customer existed in SQL Accounting Database
  ```
  {
    "docno": "string",
    "code": "string",
    "docdate": "2025-08-24",
    "paymentmethodname": "string",
    "docamt": 0,
    "knockoffivno": "string",
    "knockoffamt": 0
  }
  ```
  <img width="1598" height="630" alt="image" src="https://github.com/user-attachments/assets/723e4b4b-6af9-4d79-acc7-e1b683740935" />

- Result
  <img width="1588" height="665" alt="image" src="https://github.com/user-attachments/assets/15665977-bc02-469a-978e-0dc28baad018" />

#### Get SupplierPayments by DocNo
- Get SupplierPayments by DocNo from SQL Accounting Database
- Call API endpoint => {{baseUrl}}/api/SupplierPayments/GetSupplierPaymentByDocNo/{docNo}
  <img width="1602" height="558" alt="image" src="https://github.com/user-attachments/assets/eb1878ad-886c-4885-883f-9b9e2d58c32b" />
  
- Result:
  <img width="1595" height="652" alt="image" src="https://github.com/user-attachments/assets/8ff06097-5e19-482b-be2b-202419c722dc" />

#### Delete SupplierPayment
- Delete SupplierPayment in SQL Accounting Database
- Call API endpoint => {{baseUrl}}/api/SupplierPayments/DeleteSupplierPayment/{docNo}
  <img width="1591" height="518" alt="image" src="https://github.com/user-attachments/assets/d2504b3e-3794-4d36-a386-ec26b5f4077b" />

- Result:
  <img width="1614" height="425" alt="image" src="https://github.com/user-attachments/assets/24ff2ede-bba7-4c2b-8462-f561b8ea937e" />

