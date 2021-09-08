# **AuthTenant - External Docs**
<br>

<img src="https://www.riset.ai/img/risetai_logo.72c56424.png"
     alt="Riset.ai icon"
     style="float: left; 
            margin-right: 10px; 
            max-width:256px; 
            max-height:256px;"/>
<br><br><br>

## **Strictly Confidential** - v.202109061015

## ---------------------------------------
## **Base URL**
**https://riset.luqmanr.xyz/oauth**
<br>
**https://api.riset.ai/oauth**
## ---------------------------------------
<br>

## **1. POST `/client/login`**
### **Description**
<p>Endpoint ini digunakan untuk melakukan operasi-operasi yang berhubungan dengan akun di <strong>AuthTenant</strong></p>
<p>Untuk sekarang, fungsionalitas terbatas untuk request <strong>Accesstoken</strong></p>
<p>Akan me-generate <strong>Accesstoken</strong> baru setiap kali mendapatkan request, disarankan untuk dicatat</p>
<br>

### **Request**
#### > Headers
| KEY               | VALUE                 |
| :---              | :---                  |
| **Content-Type**  | `application/x-www-form-urlencoded` |
#### > Body
+ `x-www-form-urlencoded`

| KEY               | VALUE                 |
| :---              | :---                  |
| **client_id**     | `riset.ai`              |
| **password**      | `#password`    |
<br>

### **Response**
#### > Headers
+ `Content-Type "application/json"`
#### > Body
```json
JSON Body
{
    "access_token": "eyJhbGciOiJSUzI1NiIsIn..."
}
```
<br>


## **2. POST `/token/revoke`**
### **Description**
<p>Endpoint ini digunakan untuk me-revoke <strong>Accesstoken</strong> yang pernah di-generate. <strong>Accesstoken</strong> akan dimasukkan ke dafatar <strong>Blacklist</strong></p>
<p>Digunakan jika <strong>Accesstoken</strong> bocor ke pihak lain, dan ingin di-revoke autorisasi-nya</p>
<br>

### **Request**
#### > Headers
| KEY               | VALUE                 |
| :---              | :---                  |
| **Accesstoken**   | `access token        `|
| **Content-Type**  | `application/x-www-form-urlencoded` |

#### > Body
+ `x-www-form-urlencoded`

| KEY               | VALUE                 |
| :---              | :---                  |
| **client_id**     | `riset.ai`            |
| **password**      | `#hashed-password`    |
<br>

### **Response**
#### > Headers
+ `Content-Type "application/json"`
#### > Body
```json
JSON Body
{
    "status_message": "Success Revoke Token"
}
```
<br>
