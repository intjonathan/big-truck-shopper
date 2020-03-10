# big-truck-shopper

Consume a VIN and emit the payload and build sheet. Plan to support both Ram and Ford searches.

## RAM

Thanks to: https://www.ramforumz.com/threads/build-sheet-printout.248497/

```bash
curl 'https://www.ramtrucks.com/towingws/TowingServlet?vin=3C63R3FL5JG254992&serviceType=JSON&action=TOWINGINFOBYVIN' | jq
  % Total    % Received % Xferd  Average Speed   Time    Time     Time  Current
                                 Dload  Upload   Total   Spent    Left  Speed
100   840  100   840    0     0   3105      0 --:--:-- --:--:-- --:--:--  3111
{
  "data": {
    "status": "success",
    "brand": {
      "description": "RAM",
      "year": {
        "value": "2018",
        "vin": "3C63R3FL5JG254992",
        "vehicle": {
          "bodyModel": "D28R91",
          "cpos": "2TM",
          "model_desc": "RAM 3500 LARAMIE LONGHORN CREW CAB 4X4 6'4\" BOX",
          "model_long_desc": "RAM 3500 LARAMIE LONGHORN CREW CAB 4X4 6'4\" BOX",
          "sales_eng": "ETK",
          "eng_desc": "6.7L I6 Cummins Turbo Diesel Engine",
          "eng_long_desc": "6.7-Liter I6 Cummins? Turbo Diesel Engine",
          "sales_transm": "DF2",
          "transm_long_desc": "AISIN 6-Speed Automatic Transmission",
          "n_tow_srw_drw": "WL1",
          "c_opt_srw_drw": "S",
          "axle": {
            "sales_axle": "DMR",
            "axle_desc": "3.42 Axle Ratio",
            "axle_long_desc": "3.42 Axle Ratio",
            "max_payload": "3526.26",
            "GVWR": "11700",
            "GCWR": "25300.00",
            "BASE_CURB_WT": "7835.78",
            "max_towing": "17126.26",
            "axle_front_wt": "6000",
            "axle_rear_wt": "7000",
            "TOWOPT_PKG": {
              "code": "U  ",
              "Description": ""
            }
          }
        }
      },
      "division": "R"
    }
  }
}
```

Build sheet PDF:
 https://www.ramtrucks.com/webselfservice/BuildSheetServlet?vin=3C63RRHL7JG182869

In the PDF, search for:

* `Towing Technology Group`
  * Upgraded Door Trim Panel
  * Power Black Trailer-Tow Mirrors w/ Power Fold-Away
  * Power-Heated Mirrors with Power Fold-Away
  * Center Stop Lamp with Cargo View Camera
  * Mirror-Mounted Auxiliary Reverse Lamps
  * Gloss Black Billets with Chrome Grille
  * Surround-View Camera System
  * Blind-Spot w/Tag Trailer & Cross-Path Detection
  * Trailer Reverse Guidance
* `Safety Group`
* `Gooseneck Towing Prep Grp`
* `Cummins HO Turbo Diesel`
* `Tire Pressure Information System`
* `Crew Cab`
* `8 FT. Cargo Box`
* `Single Rear Wheel Group`
* `Trailer Brake Control`
* `GVW Rating - 14000`?

And maybe:

* `Heated Front Seats`
* `Mirrors-Tow Pwr Adj/Fold/Heat`

## Ford

A Fort ETIS account is required. Sign up [here](http://www.etisorigin.ford.com/home.do).

Manual steps: Visit http://www.etisorigin.ford.com/vehicleRegSelector.do, enter the VIN and expand the `Primary` and `Minor Features` boxes on the response page. Ford does NOT emit the door-sticker load ratings that I can find, so you'll need to use the order guide (here's the [2020 Super Duty one](https://media.ford.com/content/dam/fordmedia/North%20America/US/product/2020/f-series-super-duty/2020-Super-Duty-Order-Guide.pdf)) to figure out the options and payload ratings that you might require.
