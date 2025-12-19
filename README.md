# Llama.cpp Vulkan

This repository contains a PowerShell script (`update-llamacpp-vulkan.ps1`) that automates downloading and installing the latest Windows Vulkan‑enabled binaries of **llama.cpp** from GitHub.

## Features

- Downloads the most recent `bin-win-vulkan-x64.zip` release from `https://github.com/ggml-org/llama.cpp/releases/latest`.
- Extracts the archive into a dedicated folder under `C:\Users\<User>\apps\llamacpp-vulkan`.
- Adds that folder to the user’s `PATH` automatically.
- Cleans any previous installation before extracting the new files.
- Verifies the installation by running `llama-server.exe --version`.

## Environment this is used on

- AMD Ryzen 5 5600X
- AMD Radeon RX 6800 16GB (Reference design by Sapphire)
- 32 GB DDR4 - 3600 MHz

## Prerequisites

- Windows 10/11
- PowerShell 5.1+ (built‑in PowerShell or PowerShell Core)
- An internet connection

## Installation

1. Open PowerShell (no administrative privileges required).

2. Run the script:

   ```powershell
   .\update-llamacpp-vulkan.ps1
   ```

3. The script will:

   1. Create the directory `C:\Users\<User>\apps\llamacpp-vulkan` (or clean it if it already exists).
   2. Download the latest `bin-win-vulkan-x64.zip`.
   4. Extract the contents into the directory.
   5. Append the directory to the user’s `PATH` if it isn’t already present.
   6. Verify the installation by executing `llama-server.exe --version`.

4. After the script completes, you can launch `llama-server.exe` from any terminal without providing a full path.

> **Tip**  
> If you open a new PowerShell window after running the script, the updated `PATH` will be available immediately.

## Usage

```powershell
# Example: Run the server with a local GGML model
llama-server.exe --model "C:\models\ggml-model.bin" --prompt "Hello, world!"
```

Replace `--model` with the path to any supported GGML model.

## Contributing

Pull requests and issue reports are welcome. Feel free to suggest enhancements, bug fixes, or additional documentation.

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.