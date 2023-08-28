# WBCE CMS Stored XSS v1.6.1

## Author: (Sergio)

**Description:** WBCE CMS 1.6.1 is affected by a Cross-Site stored scripting (XSS) vulnerability that allows attackers to execute arbitrary code via a payload crafted in the Intro Page parameter in the Pages menu. The payload will be executed on the main page independent of the user's session, so accessing the home web with another user will also execute the payload.

---

### POC:


When logging into the panel, we will go to the "Modify Intro Page" section off Pages [(http://localhost/wbce/wbce/admin/pages/index.php)]

![XSS_IntroPage](https://github.com/sromanhu/WBCE-CMS-Stored-XSS---Pages-Menu/assets/87250597/a58d922c-5d99-4396-b5bc-02b690817fd8)


We edit the body configuration where we add the XSS payload:


### XSS Payload:

```js
<svg onload=alert(1)> "><svg onload=alert(1)// "onmouseover=alert(1)// "autofocus/onfocus=alert(1)//
```


In the following image you can see the embedded code that executes the payload in the main web:

![XSS_payload](https://github.com/sromanhu/WBCE-CMS-Stored-XSS---Pages-Menu/assets/87250597/f745c9c0-3ea5-49f8-9e8f-2be2cb8623a6)


When clicking on "View Site" or accessing the home page, the payload is executed:
![XSS](https://github.com/sromanhu/WBCE-CMS-Stored-XSS---Pages-Menu/assets/87250597/47aa2bd2-247a-4173-9b4c-5d08dd9fbe35)


If we log in with another user, the payload also skips:

![XSS_Stored](https://github.com/sromanhu/WBCE-CMS-Stored-XSS---Pages-Menu/assets/87250597/299b7e4c-230d-448f-bbbc-43d9e89010db)


![XSS](https://github.com/sromanhu/WBCE-CMS-Stored-XSS---Pages-Menu/assets/87250597/be8c8b55-3cd4-4382-853e-f4986d69a469)


</br>
