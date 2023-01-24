# HTML smuggling is not an evil, it can be useful

### File Smuggling Builder
This is a self-contained HTML app, supports Windows, Mac, Linux and mobile.

It adopts HTML smuggling technique, which leverages HTML 5 and JavaScript to embed encoded file into HTML file, when user run the JavaScript code in browser, it decodes the embedded payload, which, in turn, assembles the target file on the destination device.

You can convert target file to HTML encoded format, with password protected, then use it in email attachment or file download from web.

###### 1a. Choose target file `putty.exe`, then generate `putty.exe.html`
![alt text](https://github.com/eddiechu/File-Smuggling/raw/main/image/screen2.PNG?raw=true)
#
###### 1b. Open `putty.exe.html`, then retrieve `putty.exe`
![alt text](https://github.com/eddiechu/File-Smuggling/raw/main/image/screen3.PNG?raw=true)
#
###### 2a. Choose target file `Sample Document.docx`, then generate `Sample Document.docx.html`
![alt text](https://github.com/eddiechu/File-Smuggling/raw/main/image/screen4.PNG?raw=true)
#
###### 2b. Open `Sample Document.docx.html`, then retrieve `Sample Document.docx`
![alt text](https://github.com/eddiechu/File-Smuggling/raw/main/image/screen5.PNG?raw=true)

### HTML Smuggling Code

###### Use of JavaScript Blob
When working with Javascript, the file can be created by using a Javascript Blob. A Blob is a representation of payload.
```
  var bobject = new Blob([payload], {type: 'octet/stream'});
```

###### Using the URL.createObjectURL
It invoking the click action from within the Javascript, we mimic the user clicking on the link and starting the file download

```
  var hiddenobject = document.createElement('a');
  var url = window.URL.createObjectURL(bobject);
  hiddenobject.href = url;
  hiddenobject.download = targetfilename;
  hiddenobject.click();
```

Due to encoded patterns, no malicious content passes through the network, bypassing email scanners, proxies and sandboxes.


https://attack.mitre.org/techniques/T1027/006/

#html smuggling
#payload
#javascript
