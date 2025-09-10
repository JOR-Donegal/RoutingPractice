# Build

For the exercise in this session, write your commands in Notepad++ and copy & paste into the terminal. Once configurations get complex, writing at the terminal is inefficient.Open a new network in GNS3 called save as **eBGP**My plan is as shown below.![](https://www.gitbook.com/cdn-cgi/image/dpr=2,width=760,onerror=redirect,format=auto/https%3A%2F%2Ffiles.gitbook.com%2Fv0%2Fb%2Fgitbook-x-prod.appspot.com%2Fo%2Fspaces%2Fh1WE7UnEWayPUCZOtiqe%2Fuploads%2F0564YU8HvsEnqfu4U7L8%2Fimage.png%3Falt%3Dmedia%26token%3De37df8d8-bc15-42f8-8909-f8a99ff2608a)​Each customer AS has its own IP address prefix allocation.

The link networks are unimportant; however, I give them for completeness.

| Customer      | AS | IP Prefix  |
| ------------- | -- | ---------- |
| Data Center 4 | 4  | 4.4.4.0/24 |
| Corporate 5   | 5  | 5.5.5.0/24 |
| Corporate 6   | 6  | 6.6.6.0/24 |

The link networks are unimportant; however, I give them for completeness.

<table><thead><tr><th>Router</th><th width="63" data-type="number">AS</th><th width="149">IP Address</th><th width="64"></th><th></th><th width="56" data-type="number">AS</th><th>IP Address</th></tr></thead><tbody><tr><td>Router1</td><td>1</td><td>192.168.12.1</td><td>&#x3C;-></td><td>Router2</td><td>2</td><td>192.168.12.2</td></tr><tr><td>Router1</td><td>1</td><td>192.168.13.1</td><td>&#x3C;-></td><td>Router3</td><td>3</td><td>192.168.13.3</td></tr><tr><td>Router1</td><td>1</td><td>192.168.14.1</td><td>&#x3C;-></td><td>Router4</td><td>4</td><td>192.168.14.4</td></tr><tr><td>Router2</td><td>2</td><td>192.168.23.1</td><td>&#x3C;-></td><td>Router3</td><td>3</td><td>192.168.23.3</td></tr><tr><td>Router2</td><td>2</td><td>192.168.24.2</td><td>&#x3C;-></td><td>Router4</td><td>4</td><td>192.168.24.4</td></tr><tr><td>Router2</td><td>2</td><td>192.168.25.2</td><td>&#x3C;-></td><td>Router5</td><td>5</td><td>192.168.25.5</td></tr><tr><td>Router3</td><td>3</td><td>192.168.36.3</td><td>&#x3C;-></td><td>Router6</td><td>6</td><td>192.168.36.6</td></tr></tbody></table>



<figure><img src="../.gitbook/assets/image.png" alt=""><figcaption></figcaption></figure>
