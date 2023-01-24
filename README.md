# HTML smuggling is not an evil, it can be useful

## File Smuggling Builder
It adopts HTML smuggling technique, which leverages HTML 5 and JavaScript to embed target file (base64 encoded) into HTML file, when user run the JavaScript code in browser, it decodes the embedded payload, which, in turn, assembles the target file on the destination device.

Due to encoded patterns, no malicious content passes through the network, bypassing email scanners, proxies and sandboxes.

###### Use of JavaScript Blob
When working with Javascript, the file to be downloaded can be created by using a Javascript Blob. A Blob is a representation of payload.

``var bobject = new Blob([payload], {type: 'octet/stream'});``

###### Using the URL.createObjectURL
It invoking the click action from within the Javascript, we mimic the user clicking on the link and starting the file download

``var url = window.URL.createObjectURL(bobject);
hiddenobject.href = url;
hiddenobject.click();``




#html smuggling
#payload
#javascript
