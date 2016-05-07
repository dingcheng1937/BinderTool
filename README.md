# BinderTool
A Dark Souls III bdt, bhd, bnd, dcx and sl2 unpacking tool

Binaries can be downloaded under [releases](https://github.com/Atvaark/BinderTool/releases).

If you are looking for the Dark Souls II release check out the [v0.3](https://github.com/Atvaark/BinderTool/tree/v0.3) branch.

## Progress
- [X] Fix decrypting and unpacking DS III files.
- [ ] Create a dictionary
  - [x] Extract file names statically from the application
  - [ ] Extract file names statically from the archive files
  - [ ] Extract file names dynamically from the application
  - *Hooking the hash function and logging all the valid files is probably the right way. Unfortunately the function is inlined at lots of locations in the application. (Search for "imul 37")* 

### Dictionary Progress

| archive   | found names | total names | found percentage |
| :---      | ---:        | ---:        | ---:             |
| data1     |         671 |        2110 |           31,80% |
| data2     |         522 |        2140 |           24,39% |
| data3     |         481 |         673 |           71,47% |
| data4     |         476 |         951 |           50,05% |
| data5     |        3664 |        6755 |           54,24% |
| **total** |    **5814** |   **12629** |       **46,04%** |

## Requirements
```
Microsoft .NET Framework 4.5
```

## Usage
```
BinderTool input_file_path [output_folder_path]
```
If no output folder path is specified then the files are unpacked in a folder called after the archive that is getting unpacked.

## Examples

Unpacking an encrypted bdt file. This requires the corresponding .bhd files to be in the same folder.
```
BinderTool Data1.bdt
```

Unpacking an unencrypted bdt file. This requires the corresponding bhd file to be in the same folder.
```
BinderTool t10_23_00_00.tpfbdt
```

Unpacking an encrypted bhd file. This requires the corresponding KeyCode.pem files to be in the same folder.
```
BinderTool Data1.bhd
```

Unpacking a bnd file
```
BinderTool c0001.bnd
```

Unpacking a dcx file
```
BinderTool 01.febnd.dcx
```
