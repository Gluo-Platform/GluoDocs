# Server Side

For more elaborate applications, a backend is necessary.


## Validating requests

It is normal that you do not want everyone to be able to make a request. For 
that you can use the `key` provided by 
[App Instances](/docs/HTTP_API_RESOURCES/post.md#app-instance) as 
authorization. This is some core data, signed by the API. Using this public key

```shell
-----BEGIN PUBLIC KEY-----
MIIBIjANBgkqhkiG9w0BAQEFAAOCAQ8AMIIBCgKCAQEAmt7HfN0/bB/v30/Eatpt
b1DumU/l893SNwKyWr15BaAwUmRK5VctMA+FSVTj3I1CAzpYcMVtoEaZIaNTcO1j
h8yClUYw7ZuMrUhUuZDq5HC4aXHJ9No0P7e9s4dLhiktUr4fdy9krE+RUPnGFOUF
iNj6lP0L4dCDV4fxTljg9ezn+O5oTAYv3t56n7fDpbw1HjBaCU9d30t4lSmav1Ja
TkCAOcmWYIjLyeWsc45hmudGqJTyXuoFkqBTD9IqcjiIEoCiTsAMA3PR2/wbtjOJ
pJY6wAqmVpDBsGu3fnvS9P6r6NgsbWYTOANKO4m87ry3ZEq9Y3kygNvErnMq9n+t
3QIDAQAB
-----END PUBLIC KEY-----
```

you can validate the following data, against the key.

```
{app_id}.{post_id}.{user_id} 
```

{% tabs %}

{% tab title="Python" %} 
```py
from cryptography.hazmat.primitives.asymmetric import padding, rsa
from cryptography.hazmat.primitives import hashes, serialization
import hashlib


PUBLIC_KEY: rsa.RSAPublicKey


with open("public_key.pem", "rb") as key_file:
    # Ignore type because load_pem_public_key does not know what exact type it
    # will return (depends on the contents of the file).
    PUBLIC_KEY = serialization.load_pem_public_key(key_file.read()) # type: ignore


def verify(singature: bytes, app_id: str, post_id: str, user_id: str) -> None:
    data = f"{app_id}.{post_id}.{user_id}".encode("utf-8")

    PUBLIC_KEY.verify(singature, data, padding.PSS(
        mgf=padding.MGF1(hashes.SHA256()),
        salt_length=padding.PSS.MAX_LENGTH
    ), hashes.SHA256())
```
{% endtab %}

{% tab title="TypeScript" %}
```ts
// idk lol
```
{% endtab %}

{% endtabs %}
