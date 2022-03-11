# Generate Burner Wallet with Web3.Unity

```c#
using System.Collections;
using System.Collections.Generic;
using UnityEngine;
using System.Numerics;

public class BurnerWallet : MonoBehaviour
{
    void Start()
    {
        string privateKey = GenerateBurnerWallet();
        print("Private Key: " + privateKey);
        string account = Web3PrivateKey.Address(privateKey);
        print("Account: " + account);
    }

    private string GenerateBurnerWallet()
    {
        // generate 256 bit random number
        string x = "";
        for (int i = 0; i < 77; i++) {
            x += Random.Range(0, 9).ToString();
        }
        // convert string to BigInteger
        BigInteger bigInt = BigInteger.Parse(x);
        // convert BigInteger to hex string
        string hex = bigInt.ToString("X");
        // prefix with 0x
        return "0x" + hex;
    }
}
```
