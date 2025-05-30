# XAPK SSL Unpinning Tool for Flutter Apps

This tool helps you bypass SSL pinning in Flutter applications packaged as XAPK files. It's particularly useful for security testing and debugging purposes.

## Prerequisites

- Python 3.x
- Java Runtime Environment (JRE)
- [Uber APK Signer](https://github.com/patrickfav/uber-apk-signer)
- [reflutter](https://github.com/Impact-I/reFlutter) tool

## Installation

1. Clone this repository:
```bash
cd xAPK-SSL-Unpinning-Flutter
```

2. Make sure you have all prerequisites installed:
   - Install Python 3.x
   - Install Java Runtime Environment
   - Download Uber APK Signer
   - Install reflutter tool

3. On first run, the tool will prompt you for the path to your Uber APK Signer JAR file.

## Usage

Run the tool with the path to your XAPK file:

```bash
python xsigner.py path/to/your/app.xapk
```

The tool will:
1. Extract the XAPK file
2. Let you choose which APK to modify
3. Run reflutter to bypass SSL pinning
4. Sign the modified APK
5. Repackage everything into a new XAPK file

The output will be saved as `xflutter_[original_name].xapk` in the same directory.

## How It Works

1. **Extraction**: The tool extracts the XAPK file to a temporary directory
2. **APK Selection**: You can choose which APK file to modify
3. **SSL Unpinning**: Uses reflutter to bypass SSL pinning in the Flutter app
4. **Signing**: Removes the original signature and signs the APK with a new key
5. **Repackaging**: Creates a new XAPK file with the modified APK

## Directory Structure

The tool creates temporary directories during processing:
- `tmp_flutter/xapk`: Contains extracted XAPK contents
- `tmp_flutter/unsigned`: Stores unsigned APK files
- `tmp_flutter/apk`: Contains signed APK files

These directories are automatically cleaned up after the process completes.

## Configuration

The tool uses a `config.json` file to store the path to your Uber APK Signer. This is created automatically on first run.

## Notes

- This tool is intended for security testing and debugging purposes only
- Always ensure you have permission to test the target application
- The tool requires network access to perform SSL unpinning
- Make sure to keep your Java and Python installations up to date

## Troubleshooting

If you encounter issues:
1. Ensure all prerequisites are properly installed
2. Check that the XAPK file is valid and not corrupted
3. Verify that you have write permissions in the directory
4. Make sure Java is properly installed and accessible from the command line

## License

[Add your license information here]

## Disclaimer

This tool is provided for educational and security testing purposes only. Always ensure you have proper authorization before testing any application. 