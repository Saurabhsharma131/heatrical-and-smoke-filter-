# heatrical-and-smoke-filter-
file
its my qumfuuuuo




#include <ESP8266WiFi.h>
#include <ESP8266HTTPClient.h>
 
const char* ssid = "*yaha appne hotspot ka naam daal dio";
const char* password = "yaha uska password";
String REQ="";
int tempce;
void setup () {
 
Serial.begin(9600);
WiFi.begin(ssid, password);
 
while (WiFi.status() != WL_CONNECTED) {
 
delay(1000);
Serial.print("Connecting..");
 
}
 
}
 
void loop() {
 
if (WiFi.status() == WL_CONNECTED) { //Check WiFi connection status
 
HTTPClient http;  //Declare an object of class HTTPClient
tempce=tt();
REQ=REQ+"http://homotaxic-march.000webhostapp.com/stegano/band.php?temp=";
REQ=REQ+tempce;
REQ=REQ+"&pulse=plug%20sensor%20in";
http.begin(REQ);
int httpCode = http.GET();
if (httpCode > 0) { //Check the returning code
String payload = http.getString();   //Get the request response payload
Serial.println(payload);                     //Print the response payload
}
http.end();   //Close connection
 
}
 
delay(3000);    //Send a request every 3 seconds
 
}
