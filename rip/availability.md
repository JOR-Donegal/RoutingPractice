# Availability

We had 6 links; we only have 3 left working. This is called N+N redundancy, we had double the links we needed. In the real world, this would be very expensive but might still be done in mission critical locations. It would be more normal to have a primary and backup link between two sites. We try to make redundant links fully diverse. This means we would not use the same technology, path, supplier, carrier etc. for our two links.

&#x20;Typically, in Donegal, we might use a carrier for our primary link, currently over a broadband packet technology. We might use a second carrier for our second link, using a completely different technology. For example:

Link1 could be a broadband wireless link from E-Net and Link2 could be a dial-up ISDN line from Eir; or Link1 could be a wireless last mile link and Link2 could over Eir DSL.

&#x20;Have a look at the link reliability table below for an individual link. The availability figure of a link is normally provided by the carrier and will be part of the SLA for the link.

<figure><img src="../.gitbook/assets/image (12).png" alt=""><figcaption></figcaption></figure>

* A 99% available link is referred to as having two “nines”.
* A 99.9% available link is referred to as having three “nines”.
* A 99.99% available link is referred to as having four “nines”.
* A 99.999% available link is referred to as having five “nines”.

&#x20;If we have two links in series, we <mark style="color:red;">reduce</mark> the availability of the overall link.&#x20;

The overall availability (_A_) is equal to _A1\*A2_, or in this case 99\*99.9=98.901%

<figure><img src="../.gitbook/assets/image (13).png" alt=""><figcaption></figcaption></figure>

The overall link is less reliable than either of its components, as both components must be operating for the link to work.

If we have two links in parallel, we <mark style="color:green;">increase</mark> the availability of the overall link.

<figure><img src="../.gitbook/assets/image (14).png" alt=""><figcaption></figcaption></figure>

The overall availability (_A_) is equal to _1-(1-A1)\*(1-A2)_, or in this case, 1-(1-.99)\*(1-.999)=99.999%

The overall link is more reliable than either of its components as if either component is operating the link will work. These are the basic principles behind the reliability of many modern systems and communications links.
