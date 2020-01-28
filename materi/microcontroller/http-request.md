# HTTP Request

## 1. Penjelasan

Setelah NodeMCU tersambung ke wifi, kita dapat mengirim atau meminta data ke internet

## 2. Cara Melakukan HTTP Request

Berikut cara untuk melakukan http request pada micropython

```python
# import module
import urequests

# mengirim GET request
response = urequests.get("URL")
print(response.json())

# mengirim POST request
response = urequests.post("URL", data)
print(response.json())

# mengirim PUT request
response = urequests.put("URL", data)
print(response.json())

# mengirim DELETE request
response = urequests.delete("URL")
print(response.json())
```
