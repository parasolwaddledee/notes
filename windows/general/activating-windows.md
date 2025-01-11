# Activating Windows

## Select Product Key

Choose the appropriate product key for your Windows edition:

- **Windows 11 Pro**: W269N-WFGWX-YVC9B-4J6C9-T83GX
- **Windows 11 Enterprise**: NPPR9-FWDCX-D2C8J-H872K-2YT43
- **Windows Server 2025 Standard**: TVRH6-WHNXV-R9WG3-9XRFY-MY832
- **Windows Server 2025 Datacenter**: D764K-2NDRG-47T6Q-P8T8W-YP6DF

For additional product keys, refer to: [Key Management Services (KMS) client activation and product keys](https://learn.microsoft.com/en-us/windows-server/get-started/kms-client-activation-keys).

## Upgrade Windows Edition

:::info
This step is only required for the evaluation edition of Windows Server.
:::

1. Display Windows editions that the current installation can be upgraded to:

    ```
    Dism.exe /Online /Get-TargetEditions
    ```

2. Upgrade to the target edition and restart the computer:

    ```
    Dism.exe /Online /Set-Edition:<Windows Edition> /ProductKey:<Product Key> /AcceptEula
    ```

## Activate Windows

1. Install the product key:

    ```
    slmgr.vbs /ipk <Product Key>
    ```

2. Specify the KMS server (default port: TCP 1688):

    ```
    slmgr.vbs /skms <KMS Server>:<Port>
    ```

3. Activate Windows:

    ```
    slmgr.vbs /ato
    ```

4. Verify the license information:

    ```
    slmgr.vbs /dlv
    ```
