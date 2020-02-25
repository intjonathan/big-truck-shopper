# ram-truck-shopper
Consume a VIN and emit the payload and build sheet 

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
```bash
curl https://www.ramtrucks.com/webselfservice/BuildSheetServlet?vin=3C63RRHL7JG182869
<returns PDF
```
