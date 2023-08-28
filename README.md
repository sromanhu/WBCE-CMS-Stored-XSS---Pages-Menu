# CSZ CMS Stored XSS v1.3.0

## Author: (Sergio)

**Description:** CSZ CMS 1.3.0 is affected by a Stored Cross-Site Scripting (XSS) vulnerability that allows attackers to execute arbitrary code via a crafted payload to the Additional Meta Tag parameter in the Site Settings Menu that will appear both on the main page and on the subpages. 

---

### POC:


When logging into the panel, we will go to the "Site Settings" section off General Menu [(http://localhost/cszcms/admin/settings)]

![image](https://github.com/sromanhu/CSZ-CMS-Stored-XSS---Site-Settings/assets/87250597/a7b3bc1d-5f87-4614-8193-946278bb3af3)





We edit that Site Settings that we have created and see that we can inject arbitrary Javascript code in the Additional Meta Tag field.


### XSS Payload:

```js
<img src=1 onerror=alert("XSS")
```


In the following image you can see the embedded code that executes the payload in the main web and the subpages:

![image](https://github.com/sromanhu/CSZ-CMS-Stored-XSS---Site-Settings/assets/87250597/222c99f0-c00e-43d5-a46e-7d7455d2b214)


![image](https://github.com/sromanhu/CSZ-CMS-Stored-XSS---Site-Settings/assets/87250597/1d5272cc-3f41-48a4-9a4c-19db4e744eda)


![image](https://github.com/sromanhu/CSZ-CMS-Stored-XSS---Site-Settings/assets/87250597/d475b79d-0e6e-4f7f-a8e1-ca361515c009)


![image](https://github.com/sromanhu/CSZ-CMS-Stored-XSS---Site-Settings/assets/87250597/4bb0d957-3ab9-4872-bdde-dc5a53160fb6)


If we log in with another user, the payload also skips:

![image](https://github.com/sromanhu/CSZ-CMS-Stored-XSS---Site-Settings/assets/87250597/3af19bb4-e666-48ca-a1de-9914f3997771)



</br>
