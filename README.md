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

#### Delete CustomerPayment
- Delete CustomerPayment in SQL Accounting Database
- Call API endpoint => {{baseUrl}}/api/CustomerPayments/DeleteCustomerPayment/{docNo}
  <img width="1604" height="519" alt="image" src="https://github.com/user-attachments/assets/745285fe-dc30-4961-be3f-a653e4bdaf03" />

- Result:
  <img width="1606" height="379" alt="image" src="https://github.com/user-attachments/assets/bf03fbe7-db73-4251-8064-11b8b979a93f" />



