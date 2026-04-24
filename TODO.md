# TODO

## Add Brands

- Add missing major Brazilian refrigerator brands:
  - `Philco`
  - `Continental`
- Source specs from official manufacturer pages first, then major Brazilian retailers.
- Keep `fridges.json`, `fridge-types.ts`, and `models/*.md` consistent.

## Add Confirmed / Likely Missing Models

High priority narrow/compact candidates:

- `Electrolux`: `IB6S`, `RE31`, `TF38`, `TF44`, `IF44`, `IF44S`
- `HQ`: `HQ-140RDF` (`49 cm` wide), `HQ-360RFF` (`54.9 cm` wide)

Other current retailer/manufacturer signals:

- `Electrolux`: `DB44`, `TF70S`, `IB45`, `IB45S`, `IB51S`, `IB7S`, `IB7B`, `IQ8IB`
- `Brastemp`: `BRM44HK`, `BRM45JB`, `BRM54JB`, `BRM54HK`, `BRE85MB`
- `Panasonic`: `NR-BB41PV1T`, `NR-BB53GV3B`, `NR-BB53GV3M`, `NR-BB53PV3X`, `NR-BT50BD3W`, `NR-BT50BD3X`, `NR-BB64PV1X`
- `Midea`: `MD-RT580MTA461`, `MDRS761MYD461`
- `LG`: `GN-B372PFM`, `GN-B372PQW`, `GN-B452PFF`, `GC-B569NQL`, `GC-L257SLP`, `GC-X257CSHS`
- `Samsung`: `RB33A307031/AZ`, `RT38`, `RT42`, `RT53DG6650S9FZ`, `RB50`, `RS57DG4100M9AZ`, `RS60T5200S9`, `RF49A`
- `Hisense`: `RF-79W1AIQS`
- `HQ`: `HQ-426MDFF`, `HQ-480SBSFFK`
- `Consul`: `CRE44BK`

## Review Before Adding

- `Samsung RB33A307031/BZ`: may be sales-SKU variation, not separate model.
- `Panasonic NR-BB53PV3T`: official page/spec snippet looked inconsistent.

## Secondary Signals Only

Check whole-unit listings before adding:

- `Electrolux`: `IB54`, `IB54B`, `IB54S`, `IM7`, `IM7B`, `IM7S`, `IM8B`, `IM8IS`, `IQ8IS`, `IB5WS`
- `Brastemp`: `BRM45HB`, `BRM45HK`, `BRM54JK`, `BRM53HB`, `BRM53HK`
- `Consul`: `CRA35FB`, `CRM35BB`, `CRM38BB`, `CRD38DB`, `CRD38DC`, `CRD41DB`, `CRB36AB`, `CRB36AC`, `CRB36ZB`, `CRB39AB`, `CRB39AC`, `CRB39AK`, `CRG36AB`, `CRG36AC`

## Verify Existing Notes

- `models/BRM45JB.md`: replace inherited BRM44-family dimensions with official datasheet values.
- `models/NR-BB53PV3X.md`: replace inherited BB53-family dimensions with official datasheet values.
