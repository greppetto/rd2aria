# real-debrid-download-helper

A simple tool with a CLI to simplify the process of downloading torrents through Real-Debrid.com. It allows you to communicate with the Real-Debrid API to add magnet links to your account, and obtain/unrestrict their download links.

## Features

- Simple CLI
- Add magnet links to Real-Debrid
- Wait until torrent is cached and obtain unrestricted links, dynamically scaling polling rate based on torrent size
- Optionally display the unrestricted links
- Optionally dump the links into a .txt file in folder of choice
- Optionally start download of files using `aria2c`

## Build

```bash
cmake -B build -S . -DCMAKE_BUILD_TYPE=Release
cmake --build build
./build/rddl
```

## Options and Flags

    -h,     --help                      Print this help message and exit
    -t,     --token     TEXT            Set API token and save it locally
    -m,     --magnet    TEXT REQUIRED   Magnet link
    -l,     --links                     Print unrestricted links
    -o,     --output    TEXT            Specify path for output .txt file
    -a,     --aria2                     Start download using aria2

## API Token

Either pass the token using the option -t/--token, or add the following to your environment variables:

- Linux/macOS:

```bash
export REAL_DEBRID_API_TOKEN=your_token_here
./myapp
```

- Windows (PowerShell):

```powershell
$env:REAL_DEBRID_API_TOKEN=your_token_here
.\myapp.exe
```
