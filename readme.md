# XRPL Binary Deserializer
A fast, small and portable XRPL binary serialization format deserializer written in C with no dependencies.

## Serialization Format
The XRP Ledger uses a bespoke serialization format detailed here [xrpl.org](https://xrpl.org/serialization.html). This tool offers a portable C deserializer for this format.
## Requirements
This code is designed to be highly portable and efficient, therefore only the following tools are required to build it.
* gcc
* make
## Compiling
1. Clone repo.
2. Run `make`

## Running / Examples
### Arguments
```
Usage: ./xd < HEXBLOB | hex file | - for stdin >
```

### Decode a transaction
```bash
./xd 1200002280070000240013DAF5201B03CC4BC361D4D5DB3618B29F0000000000000000000000000055534400000000000A20B3C85F482532A9578DBB3950B85CA06594D168400000000000000C6940000000038C34007321EDD5551CDAD613AEB8DDBD4621B5EE66CBB0E9D322300AB8B8206208C63D562E597440BF4FBE6D56A5265430C63614AA085E4ECBB06459A22549DB978152DB3593173D07457C781DEB4BB59375255B286A0475C9CFF9772A05D40BBDE7134B43973E0381146EF659A5DEE7A1CF2DB67D0B66126B1013668DA883146EF659A5DEE7A1CF2DB67D0B66126B1013668DA8F9EA7C06636C69656E747D03726D32E1F1011230000000000000000000000000434E590000000000CED6E99370D5C00EF4EBF72567DA99F5661BFB3A00
```

### Decode Metadata
```bash
./xd 201C00000021F8E3110064561AC09600F4B502C8F7F830F80B616DCB6F3970CB79AB70975A0637F454A1173CE8365A0637F454A1173C581AC09600F4B502C8F7F830F80B616DCB6F3970CB79AB70975A0637F454A1173C0311000000000000000000000000434E59000000000004110360E3E0751BD9A566CD03FA6CAFC78118B82BA0E1E1E4110064561AC09600F4B502C8F7F830F80B616DCB6F3970CB79AB70975A063B08AC79C879E72200000000365A063B08AC79C879581AC09600F4B502C8F7F830F80B616DCB6F3970CB79AB70975A063B08AC79C87901110000000000000000000000000000000000000000021100000000000000000000000000000000000000000311000000000000000000000000434E59000000000004110360E3E0751BD9A566CD03FA6CAFC78118B82BA0E1E1E511006456AEA3074F10FE15DAC592F8A0405C61FB7D4C98F588C2D55C84718FAFBBD2604AE7220000000031000000000000000032000000000000000058AEA3074F10FE15DAC592F8A0405C61FB7D4C98F588C2D55C84718FAFBBD2604A82142252F328CF91263417762570D67220CCB33B1370E1E1E311006F56B23E5BB2E0FF41AC9FD05CAC7F7767C4AF6F40E0BA92F622F795610C50683B2FE824047A857950101AC09600F4B502C8F7F830F80B616DCB6F3970CB79AB70975A0637F454A1173C644000000310947CBC65D59AB78A1E3E5F03000000000000000000000000434E5900000000000360E3E0751BD9A566CD03FA6CAFC78118B82BA081142252F328CF91263417762570D67220CCB33B1370E1E1E51100612503CC4D1555390D885934E1F95F94A47EDAE269AEAB4B1F1ADCECF7803C11BE58D59CD5215056E0311EB450B6177F969B94DBDDA83E99B7A0576ACD9079573876F16C0C004F06E624047A8579624000000006010EF3E1E7220000000024047A857A2D00000005624000000006010EE781142252F328CF91263417762570D67220CCB33B1370E1E1E411006F56E4FF0EFB4C47C238F3EAB152275B8F1BDC55ED5A7739EC73E324B300D36C1B66E7220000000024047A85752503CC4D143300000000000000003400000000000000005583A1CB8A200A1EFCAFAA313CD0EEF0B7788B9854ED60FFB9491588935066805E50101AC09600F4B502C8F7F830F80B616DCB6F3970CB79AB70975A063B08AC79C87964400000000CE086A165D544606246BC1AB7000000000000000000000000434E5900000000000360E3E0751BD9A566CD03FA6CAFC78118B82BA081142252F328CF91263417762570D67220CCB33B1370E1E1F1031000
```

## Test Rig
The `tests/` directory contains some sample serialized objects against which JSON validation using jq is performed.
1. Build `xd` first (see above)
2. Install`jq` if you don't already have it
3. `cd tests`
4. `chmod 700 ./runtests.sh`
5. `./runtests.sh`

If you want to see the full output of each test run `./runtestsful.sh`
