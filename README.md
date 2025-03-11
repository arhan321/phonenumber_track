# Phone Number Location Tracker using Python By djncloud
Tidak Boleh disalah gunakan

## Teknologi :
```
BHS_pemrograman : Python
```
## Package yang di pake
```
phonenumbers
```
```
folium
```
```
geocoder
```
```
OpenCage
```

## Installation

Install package with pip

```bash
  pip install phonenumbers
  pip install folium
  pip install geocoder
  pip install opencage
```

Silahkan mengambil API KEY nya dari sini :  https://opencagedata.com/

Step1: Need to log in or sign up

![github1](https://user-images.githubusercontent.com/123636419/215339770-3cc5ba46-d502-42b9-9f15-856718cf22d1.PNG)

Step2: Need to click Geocoding API

![github2](https://user-images.githubusercontent.com/123636419/215339775-89aef127-2390-4f8d-8ad6-1129789eabab.PNG)

Step3: From API Keys collect API key

![github3](https://user-images.githubusercontent.com/123636419/215339773-0171d38c-b9ad-490a-95d8-47366321048a.PNG)


## Deployment

code yang perlu di sesuaikan hanya API KEY saja, itu di ambil dari OpenCage web, silahkan register setelah itu dapatkan API KEY nya...

```bash
import phonenumbers
from phonenumbers import geocoder
from phonenumbers import carrier
import opencage
from opencage.geocoder import OpenCageGeocode
import folium


key = "your key" #Geocoder API Key need to paste here "your key" 
number = input("please giver your number: ")
new_number = phonenumbers.parse(number)
location = geocoder.description_for_number(new_number, "en")
print(location)

service_name = carrier.name_for_number(new_number,"en")
print(service_name)

geocoder = OpenCageGeocode(key)
query = str(location)
result = geocoder.geocode(query)
#print(result)

lat = result[0]['geometry']['lat']
lng = result[0]['geometry']['lng']

print(lat,lng)

my_map = folium.Map(location=[lat,lng], zoom_start=9)
folium.Marker([lat, lng], popup= location).add_to(my_map)

my_map.save("location.html")

print("location tracking completed")
print("Thank you")
```

# How to run 
silahkan jalankan langsung si code python nya 
```
python3 main.py
```
sample use : 
```
 ⚡ root@DESKTOP-UO99V0J  ~/phonenumber_tracker/phonenumber_track   master  python3 main.py
please giver your number: +62 xxxxxxxx
Indonesia
Telkomsel
-2.xxxxxx 117.xxxxxxxx
location tracking completed
Thank you
```
# Happy Coding !!!!!!!!
# love OSINT & Stay White hat hacker