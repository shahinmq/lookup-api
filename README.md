<?php
$token = '';
$ip = '';
$curl = curl_init();

curl_setopt_array($curl, array(
  CURLOPT_URL => "https://lphp.ir/lookup/get/?license=$token&ip=$ip",
  CURLOPT_RETURNTRANSFER => true,
  CURLOPT_TIMEOUT => 0,
  CURLOPT_FOLLOWLOCATION => true
));

$response = curl_exec($curl);

curl_close($curl);

$response = json_decode($response);

//OUTPUT (JSON) :

{
    "remaining_request": 5001,
    "ok": true,
    "error": null,
    "ip": XXX.XXX.XXX.XXX,
    "result": {
        "country": {
            "name": "germany",
            "iso": "de",
            "geoid": 2921044
        },
        "continent": {
            "name": "europe",
            "iso": "eu",
            "geoid": 6255148
        }
    }
}
