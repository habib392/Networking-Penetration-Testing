## 🌎 Jab hum website access karte hain, kya hota hai?

Jab hum browser mein koi website type karte hain jaise `garena.com`, toh humare device se ek **request** generate hoti hai. Yeh request ek packet ki form mein nikalti hai aur Internet ke zariye server tak jaati hai. Server wapas ek **response** bhejta hai.

---

## ✉️ Request ka Flow:

### Agar **WiFi** use ho raha ho:

1. Request → Tumhara device (PC/Mobile)
2. → Tumhara Router
3. → ISP (Internet Service Provider)
4. → Garena.com ka Server

### Agar **Mobile Data (Jazz/Zong)** use ho raha ho:

1. Request → Tumhara Mobile
2. → Jazz/Zong Tower
3. → ISP ka Gateway
4. → Garena.com ka Server

Request mein kuch headers hote hain jo server ko batate hain:

* **Method**: GET, POST waghera
* **User-Agent**: Tumhara browser aur OS ka naam
* **Accept**: Kaunsa format chahiye (HTML, JSON, image etc.)
* **Accept-Language**: Kaunsi language mein content chahiye (e.g., en-US)
* Aur bhi kuch headers ho sakte hain jaise Host, Referer, Cookie etc.

---

## 📥 Response ka Flow:

### WiFi:

1. Server se response nikalta hai
2. → ISP ke paas jaata hai
3. → Tumhare router tak aata hai
4. → Tumhare device tak pahuchta hai

### Mobile Data:

1. Server se response
2. → ISP Gateway
3. → Tower tak
4. → Tumhare Mobile tak

Response mein bhi headers hote hain:

* **Status Code**: 200 OK, 404 Not Found, 403 Forbidden
* **Content-Type**: HTML, JSON etc.
* **Set-Cookie**, **Content-Length** etc.

Aur body mein hota hai actual HTML ya data jo browser render karta hai.

---

## ⚙️ HTTP Methods (Use ke sath)

### 1. **GET**

Data lene ke liye (sirf dekhna)
Example: `GET /profile?id=12`

### 2. **POST**

Server ko data bhejna (login, signup, forms)
Example: `POST /login`

### 3. **PUT**

Pura data update karna (replace)
Example: `PUT /user/12`

### 4. **PATCH**

Partial update (sirf kuch fields badalna)
Example: `PATCH /user/12`

### 5. **DELETE**

Data delete karwana
Example: `DELETE /user/12`

### 6. **HEAD**

GET jaisa hai lekin sirf headers deta hai
Example: Check karna ke file exist karti hai ya nahi

### 7. **OPTIONS**

Puchhna ke kaunse methods allowed hain
Example: `OPTIONS /login`

### 8. **CONNECT**

Tunnel banana HTTPS ke liye (via proxy)

### 9. **TRACE**

Request ko echo karta hai (debug ke liye)

---

## 🔒 Penetration Testing ke Faide:

* GET/POST mein tampering possible
* PUT/PATCH par unauthorized update test
* DELETE par access control test
* OPTIONS se methods check kar sakte hain
* Burp Suite mein sab analyze karne ka moka milta hai
* Headers se sensitive info leak detect kar sakte hain
