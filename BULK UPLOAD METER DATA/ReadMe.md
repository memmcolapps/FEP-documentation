```markdown
# New MomasPay - Bulk Meter Data Upload Guide

This document provides instructions on how to bulk upload meter data into the New MomasPay system. Following these guidelines will ensure successful data import and prevent errors.

## CSV File Format

The CSV file _must_ adhere to the following structure:

### Header Row

The first row of the CSV file _must_ be the header row, spelled exactly as follows:
```

meterNo, metersimno, transid, status, accountno, isamr, metermodel, isdualtariff, sgc, oldsgc, newtariffindex, oldtariffdual, krn1, krn2, needkct, credittypeid

```

### Field Descriptions and Constraints

| Header          | Description                                                                                                  | Data Type | Constraints                                                       |
| :-------------- | :----------------------------------------------------------------------------------------------------------- | :-------- | :---------------------------------------------------------------- |
| `meterNo`       | Meter Number                                                                                                 | Text      | Unique identifier for the meter                                 |
| `metersimno`    | Meter SIM Number                                                                                             | Text      | SIM number associated with the meter, if applicable                |
| `transid`       | Transformer ID                                                                                               | Integer   | ID obtained from the Transformer Module                         |
| `status`        | Meter Status                                                                                                 | Integer   | `0` (Pending) or `2` (Active)                                   |
| `accountno`     | Account Number                                                                                                 | Text      | Account number associated with the meter                          |
| `isamr`         | Is AMR (Automated Meter Reading) Enabled?                                                                  | Integer   | `1` (Enabled) or `0` (Disabled)                                 |
| `metermodel`    | Meter Model                                                                                                  | Text      | Meter model identifier                                            |
| `isdualtariff`  | Is Dual Tariff Enabled?                                                                                      | Boolean   | `true` or `false`                                                 |
| `sgc`           | Supply Group Code                                                                                            | Text      | Supply Group Code for the meter                                   |
| `oldsgc`        | Old Supply Group Code                                                                                        | Text      | Previous Supply Group Code (if applicable)                        |
| `newtariffindex`| New Tariff Index                                                                                             | Integer   | Index of the new tariff                                           |
| `oldtariffdual` | Old Tariff Dual                                                                                              | Text      | Old Dual Tariff (if applicable)                                   |
| `krn1`          | Key Revision Number 1                                                                                        | Text      | Key Revision Number 1 (if applicable)                            |
| `krn2`          | Key Revision Number 2                                                                                        | Text      | Key Revision Number 2 (if applicable)                            |
| `needkct`       | Need KCT (Key Change Token)?                                                                                 | Integer   | `1` (Required) or `0` (Not Required)                              |
| `credittypeid`  | Credit Type ID                                                                                               | Text      | Specifies the type of credit: `electricity`, `water`, or `gas`|

## Important Considerations

*   **Transformer Module and `transid`:**
    *   Navigate to the Transformer Module within New MomasPay.
    *   The `transid` corresponds to the unique identifier (likely the first column) listed in that module.  Ensure you use the correct ID.

*   **Status Codes:** The `status` field *must* contain only `0` for pending meters or `2` for active meters.

*   **Credit Type ID:** The `credittypeid` field *must* contain one of the three specified values: `electricity`, `water`, or `gas`. Ensure correct spelling.

*   **AMR and KCT Flags:**
    *   Use `1` to indicate enabled/required.
    *   Use `0` to indicate disabled/not required.
    *   These apply to the `isamr` and `needkct` fields respectively.

*   **Boolean Values:** Represent boolean values as `true` or `false` (case-insensitive) for the `isdualtariff` field.

## Data Validation

Always validate your data *before* uploading to prevent errors and ensure data integrity. Pay close attention to the constraints outlined above. Incorrect or missing data can lead to import failures.
```

CURRENTLY MAINTAINED BY MOSHOOD ALIMI
